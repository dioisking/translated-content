---
title: API MediaStream
slug: Web/API/Media_Streams_API
tags:
  - API
  - Audio
  - Media
  - Overview
translation_of: Web/API/Media_Streams_API
original_slug: WebRTC/MediaStream_API
---
{{DefaultAPISidebar("Media Capture and Streams")}}

L'**API Processing MediaStream**, souvent appelée _Media Stream API_ ou _Stream API_, est la partie de [WebRTC](/fr/docs/WebRTC) décrivant un flux de données audio ou vidéo, les méthodes pour les manipuler, les contraintes associées au type de données, les erreurs et succès des callbacks avec les données asynchrones, et les évènements déclenchés durant le processus.

## Concepts de base

L'API est basée sur la manipulation de l'objet {{domxref("MediaStream")}} représentant un flux de données audio ou vidéo. Typiquement, un {{domxref("MediaStream")}} est une simple chaine URL qui peut être utilisée pour référencer une donnée stockée dans un {{domxref("File")}} DOM, ou un objet {{domxref("Blob")}} crée avec {{domxref("window.URL.createObjectURL()")}}, tel que décrit dans [cette vidéo](/en-US/docs/WebRTC/taking_webcam_photos#Get_the_video).

Un {{domxref("MediaStream")}} consiste en zéro ou plus objets {{domxref("MediaStreamTrack")}}, représentant différentes **pistes** audio ou vidéos. Chaque {{domxref("MediaStreamTrack")}} peut avoir un ou plusieurs **canal**. Le canal représente la plus petite unité d'un flux média, tel un signal audio d'un haut-parleur, séparé en _gauche_ et _droite_ sur une piste audio en stéréo.

`Les objets `{{domxref("MediaStream")}} ont une seule **entrée** et une seule **sortie**. Un objet {{domxref("MediaStream")}} généré par [getUserMedia()](/en-US/docs/WebRTC/navigator.getUserMedia) est dit _local_, et sa source d'entrée provient de l'une des caméra ou microphone de l'utilisateur. Un objet {{domxref("MediaStream")}} non local peut représenter un média tel que {{HTMLElement("video")}} ou {{HTMLElement("audio")}}, un flux provenant du réseau et obtenu via l'API WebRTC [PeerConnection](/en-US/docs/WebRTC/PeerConnection_API), ou un flux créé en utilisant l'API [Web Audio](/en-US/docs/Web_Audio_API) {{domxref("MediaStreamAudioSourceNode")}}. La sortie d'un objet {{domxref("MediaStream")}} est liée à un **consommateur**. Elle peut-être un élément média tel que {{HTMLElement("audio")}} ou {{HTMLElement("video")}}, l'API WebRTC [PeerConnection](/en-US/docs/WebRTC/PeerConnection_API) ou l'[API Web Audio](/en-US/docs/Web_Audio_API) {{domxref("MediaStreamAudioDestinationNode")}}.

## Interfaces

Dans ces articles de référence, on trouvera les informations fondamentales sur les différentes interfaces qui composent l'API _Media Capture and Streams API_.

- {{domxref("BlobEvent")}}
- {{domxref("CanvasCaptureMediaStreamTrack")}}
- {{domxref("InputDeviceInfo")}}
- {{domxref("MediaDeviceKind")}}
- {{domxref("MediaDeviceInfo")}}
- {{domxref("MediaDevices")}}
- {{domxref("MediaStream")}}
- {{domxref("MediaStreamConstraints")}}
- {{domxref("MediaStreamEvent")}}
- {{domxref("MediaStreamTrack")}}
- {{domxref("MediaStreamTrackEvent")}}
- {{domxref("MediaTrackCapabilities")}}
- {{domxref("MediaTrackConstraints")}}
- {{domxref("MediaTrackSettings")}}
- {{domxref("MediaTrackSupportedConstraints")}}
- {{domxref("NavigatorUserMedia")}}
- {{domxref("NavigatorUserMediaError")}}
- {{domxref("OverconstrainedError")}}
- {{domxref("URL")}}

Les premières versions de la spécification pour Media Capture and Streams API incluaient des interfaces séparées `AudioStreamTrack` et `VideoStreamTrack`, chacunes basées sur {{domxref("MediaStreamTrack")}} et qui représentaient des types de flux différents. Celles-ci n'existent plus et il faut utiliser `MediaStreamTrack` directement à la place.

## Évènements

- {{event("addtrack")}}
- {{event("ended")}}
- {{event("muted")}}
- {{event("overconstrained")}}
- {{event("removetrack")}}
- {{event("started")}}
- {{event("unmuted")}}

## Guides et tutorials

Les articles qui suivent fournissent des manuels et guides pour utiliser cette API et réaliser des certaines tâches avec elle.

{{LandingPageListSubpages}}

## Compatibilité des navigateurs

{{Compat("api.MediaStream")}}

## Voir aussi

- [WebRTC](/fr/docs/Web/API/WebRTC_API) - la page d'introduction à l'API
- {{domxref("mediaDevices.getUserMedia()")}}
- [Prendre des clichés avec WebRTC](/fr/docs/Web/API/WebRTC_API/Taking_still_photos) : un tutoriel/une démonstration sur l'utilisation de `getUserMedia()`.
