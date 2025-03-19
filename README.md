## Problem Statement

Deepfake technology has increasingly become a tool for creating highly realistic and yet completely fabricated images and videos, posing significant privacy risks. This technology allows for the impersonation of individuals in various contexts, potentially leading to identity fraud, privacy breaches, and reputational damage for both individuals and organizations. The ease with which deepfakes can be created and disseminated, especially given the availability of open-source deepfake generation tools, exacerbates these risks. Moreover, deepfakes have found applications in malicious activities ranging from social engineering attacks to the creation of nonconsensual pornographic content, heightening concerns about privacy and security in the digital realm.

The alarming capability of deepfake technology to produce believable content from minimal real-life input (one image or mere seconds of audio) further underscores the urgency of addressing this issue. As such technologies continue to evolve at a rapid pace, outstripping efforts to regulate their use or implement effective countermeasures on social media platforms, there is a critical need for proactive solutions that empower individuals to protect their digital identities.



Here a single image from a (fake) Social profile is used to create a deepfake video from a [popular gif](https://media.giphy.com/media/12XMGIWtrHBl5e/giphy.gif)

<img src="resources/Balikabakra_cropped@0.5x.png">

***Hey Bali, do you want a promotion?***


<img src="resources/ezgif-2-44af65206a.gif">


## Proposed Solution: Deepmask

Deepmask is an innovative approach that leverages AI technology not as a tool for invasion of privacy but as a means of defense against potential abuses of digital identity through deepfakes. By enabling users to anonymize their personal information and create virtual personas or avatars with unique faces, styles, and voices, Deepmask provides a layer of protection designed to prevent individuals' likenesses from being exploited in deepfake creations.

### Try the Alpha Version
Check out our alpha release: [Deepmask Alpha](https://deepmask-backend-886097756396.us-central1.run.app)

||Professional Profile|Social Profile|
|-|-|-|
| Private images |<img src="https://raw.githubusercontent.com/A-Good-Company/deepmask/master/resources/Pasted%20image%2020240218234920.png" width="350px"> |<img src="https://raw.githubusercontent.com/A-Good-Company/deepmask/master/resources/Pasted%20image%2020240218235314.png" width="350px">|
| <img src="https://raw.githubusercontent.com/A-Good-Company/deepmask/master/resources/Pasted%20image%2020240218231839.png" width="350px"> | <img src="https://github.com/A-Good-Company/deepmask/blob/master/resources/Pasted%20image%2020240219000008.png" width="350px"> |<img src="https://raw.githubusercontent.com/A-Good-Company/deepmask/master/resources/Pasted%20image%2020240219000408.png" width="350px">|
|OpenPose Face generator template|Prompt: a good young indian office employee, black hair, male |Prompt: a funky young indian party animal, black hair, male|
| Deepmasked images, with non users anonymized <br><img src="https://raw.githubusercontent.com/A-Good-Company/deepmask/master/resources/Pasted%20image%2020240219000551.png" width="150px"> |<img src="https://raw.githubusercontent.com/A-Good-Company/deepmask/master/resources/Pasted%20image%2020240219001324.png" width="350px"> |<img src="https://raw.githubusercontent.com/A-Good-Company/deepmask/master/resources/Pasted%20image%2020240219000908.png" width="350px">|



### Technology Stack:

- **Face Generation:** Utilizing [Stable Diffusion](https://github.com/AUTOMATIC1111/stable-diffusion-webui) with **ControlNet** enabled,  and set to **ControlType**:  `OpenPose_faceonly` for generating virtual faces.
- **Face Swap:** Implementing [ReActor](https://github.com/Gourieff/sd-webui-reactor) plugin for swapping faces between images or videos.
- **Body Swap:** Employing [Segment Anything](https://github.com/continue-revolution/sd-webui-segment-anything) (SAM) model for body selection and using Stable Diffusion to anonymize or swap bodies within content.
- **Voice Swap:** [WhisperX](https://github.com/m-bain/whisperX) for text detection, [TortoiseTTS](https://github.com/neonbjb/tortoise-tts) for Speech generation

### Milestones:

1. **P0 - Face Masking:** The initial phase focuses on creating virtual avatars by generating unique faces that users can adopt in their online presence.
2. **P1 - Voice Masking:** This phase introduces the capability to alter voice recordings such that they match the generated virtual avatars while protecting the user's original voice characteristics.
3. **P2 - Auto Users Face Matching and Customized Swapping:** Enhancing user experience by automatically matching users' faces with suitable virtual avatars based on preferred features and facilitating customized face swapping.
4. **P3 - Body Masking:** The final phase extends the anonymization process to include body masking, allowing users to select and swap entire body images, further enhancing privacy and protection against deepfake exploitation.

## Use Cases

Deepmask serves a wide array of users and scenarios, offering vital solutions in several contexts:

- **Personal Privacy Protection:** Individuals concerned about their digital footprint and privacy can use Deepmask to present a virtual persona online, reducing the risk of their real images being used in deepfakes.
- **Social Media Integrity:** Content creators who wish to maintain an online presence without compromising their real-life identity can utilize Deepmask for creating content that remains true to their creative vision but disconnects from their personal identity.
- **Professional and Corporate Security:** Businesses can protect their employees' identities in digital communications, safeguarding against impersonation attacks that could lead to data breaches or financial fraud.

## Challenges & Future Directions

While Deepmask presents a promising solution against the misuse of deepfake technology, several challenges remain. These include ensuring the accessibility of the technology for non-technical users, maintaining the balance between anonymity and authenticity, and continuously adapting to evolving deepfake technologies.

Future developments could explore integrating more advanced AI techniques for even more realistic voice and face generation, improving user interfaces for easier customization of avatars, and expanding partnerships with social media platforms for broader implementation of anonymization features. Additionally, ethical considerations around the use of such technologies must be addressed continuously to ensure they are used responsibly.

[Deepmask Roadmap](https://github.com/users/A-Good-Company/projects/5)
