---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.date: 03/30/2017
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
ms.openlocfilehash: d8abfe6e34439ccf399e37c1285b7b71cebf9870
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258035"
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a><span data-ttu-id="c5bb7-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span><span class="sxs-lookup"><span data-stu-id="c5bb7-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span></span>

<span data-ttu-id="c5bb7-103">Der Sicherheitshandshake mit einem potenziellen Nachbarn war nicht erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="c5bb7-103">The security handshake with a potential neighbor was not successful.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c5bb7-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c5bb7-104">Description</span></span>  

 <span data-ttu-id="c5bb7-105">Diese Ablaufverfolgung tritt beim Herstellen einer sicheren Nachbarverbindung auf.</span><span class="sxs-lookup"><span data-stu-id="c5bb7-105">This trace occurs while attempting to establish a secure neighbor connection.</span></span> <span data-ttu-id="c5bb7-106">Dies kann aufgrund ungenügender oder falscher Anmeldeinformationen geschehen.</span><span class="sxs-lookup"><span data-stu-id="c5bb7-106">This can happen due to insufficient or incorrect credentials.</span></span>  
  
 <span data-ttu-id="c5bb7-107">PeerChannel erkennt einen einzelnen Tokentyp für eine starke Identifizierung, X.509-Zertifikate, die ein starkes Identifikationsmodell bereitstellen, das auf dem Typ der Authentifizierung und der Autorisierung basiert, der implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c5bb7-107">PeerChannel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="c5bb7-108">PeerChannel unterstützt darüber hinaus einfache Anwendungen durch die Verwendung von Kennwörtern.</span><span class="sxs-lookup"><span data-stu-id="c5bb7-108">PeerChannel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="c5bb7-109">Kennwörter können nur verwendet werden, um Zugang zu einer Sitzung zu erhalten. Die Durchführung von Nachrichtenauthentifizierung über Kennwörter ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="c5bb7-109">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="c5bb7-110">Grund hierfür ist, dass ein symmetrischer Token, den sich eine Peergruppe teilt, für die Quellenauthentifizierung schwierig und ungeeignet ist.</span><span class="sxs-lookup"><span data-stu-id="c5bb7-110">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="c5bb7-111">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="c5bb7-111">Troubleshooting</span></span>  

 <span data-ttu-id="c5bb7-112">Stellen Sie sicher, dass alle Nachbarn über geeignete Sicherheitsanmeldeinformationen verfügen.</span><span class="sxs-lookup"><span data-stu-id="c5bb7-112">Ensure that all neighbors have the appropriate security credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5bb7-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5bb7-113">See also</span></span>

- [<span data-ttu-id="c5bb7-114">Peerkanalsicherheit</span><span class="sxs-lookup"><span data-stu-id="c5bb7-114">Peer Channel Security</span></span>](../../feature-details/peer-channel-security.md)
- [<span data-ttu-id="c5bb7-115">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="c5bb7-115">Tracing</span></span>](index.md)
- [<span data-ttu-id="c5bb7-116">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="c5bb7-116">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c5bb7-117">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="c5bb7-117">Administration and Diagnostics</span></span>](../index.md)
