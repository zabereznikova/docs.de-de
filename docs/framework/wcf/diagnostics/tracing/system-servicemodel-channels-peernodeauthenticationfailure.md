---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.date: 03/30/2017
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
ms.openlocfilehash: 633f497950ab14d7715537eed8f5cc80e7a350a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33479852"
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a><span data-ttu-id="3e1a4-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span><span class="sxs-lookup"><span data-stu-id="3e1a4-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span></span>
<span data-ttu-id="3e1a4-103">Der Sicherheitshandshake mit einem potenziellen Nachbarn war nicht erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="3e1a4-103">The security handshake with a potential neighbor was not successful.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3e1a4-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e1a4-104">Description</span></span>  
 <span data-ttu-id="3e1a4-105">Diese Ablaufverfolgung tritt beim Herstellen einer sicheren Nachbarverbindung auf.</span><span class="sxs-lookup"><span data-stu-id="3e1a4-105">This trace occurs while attempting to establish a secure neighbor connection.</span></span> <span data-ttu-id="3e1a4-106">Dies kann aufgrund ungenügender oder falscher Anmeldeinformationen geschehen.</span><span class="sxs-lookup"><span data-stu-id="3e1a4-106">This can happen due to insufficient or incorrect credentials.</span></span>  
  
 <span data-ttu-id="3e1a4-107">PeerChannel erkennt einen einzelnen Tokentyp für eine starke Identifizierung, X.509-Zertifikate, die ein starkes Identifikationsmodell bereitstellen, das auf dem Typ der Authentifizierung und der Autorisierung basiert, der implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3e1a4-107">PeerChannel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="3e1a4-108">PeerChannel unterstützt darüber hinaus einfache Anwendungen durch die Verwendung von Kennwörtern.</span><span class="sxs-lookup"><span data-stu-id="3e1a4-108">PeerChannel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="3e1a4-109">Kennwörter können nur verwendet werden, um Zugang zu einer Sitzung zu erhalten. Die Durchführung von Nachrichtenauthentifizierung über Kennwörter ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="3e1a4-109">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="3e1a4-110">Grund hierfür ist, dass ein symmetrischer Token, den sich eine Peergruppe teilt, für die Quellenauthentifizierung schwierig und ungeeignet ist.</span><span class="sxs-lookup"><span data-stu-id="3e1a4-110">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3e1a4-111">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="3e1a4-111">Troubleshooting</span></span>  
 <span data-ttu-id="3e1a4-112">Stellen Sie sicher, dass alle Nachbarn über geeignete Sicherheitsanmeldeinformationen verfügen.</span><span class="sxs-lookup"><span data-stu-id="3e1a4-112">Ensure that all neighbors have the appropriate security credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e1a4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e1a4-113">See Also</span></span>  
 [<span data-ttu-id="3e1a4-114">Peerkanalsicherheit</span><span class="sxs-lookup"><span data-stu-id="3e1a4-114">Peer Channel Security</span></span>](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)  
 [<span data-ttu-id="3e1a4-115">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="3e1a4-115">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="3e1a4-116">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="3e1a4-116">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="3e1a4-117">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="3e1a4-117">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
