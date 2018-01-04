---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ffca9a587bdb32afc252f9719eb35e3139dd3f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a><span data-ttu-id="d7a81-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span><span class="sxs-lookup"><span data-stu-id="d7a81-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span></span>
<span data-ttu-id="d7a81-103">Der Sicherheitshandshake mit einem potenziellen Nachbarn war nicht erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d7a81-103">The security handshake with a potential neighbor was not successful.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d7a81-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7a81-104">Description</span></span>  
 <span data-ttu-id="d7a81-105">Diese Ablaufverfolgung tritt beim Herstellen einer sicheren Nachbarverbindung auf.</span><span class="sxs-lookup"><span data-stu-id="d7a81-105">This trace occurs while attempting to establish a secure neighbor connection.</span></span> <span data-ttu-id="d7a81-106">Dies kann aufgrund ungenügender oder falscher Anmeldeinformationen geschehen.</span><span class="sxs-lookup"><span data-stu-id="d7a81-106">This can happen due to insufficient or incorrect credentials.</span></span>  
  
 <span data-ttu-id="d7a81-107">PeerChannel erkennt einen einzelnen Tokentyp für eine starke Identifizierung, X.509-Zertifikate, die ein starkes Identifikationsmodell bereitstellen, das auf dem Typ der Authentifizierung und der Autorisierung basiert, der implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d7a81-107">PeerChannel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="d7a81-108">PeerChannel unterstützt darüber hinaus einfache Anwendungen durch die Verwendung von Kennwörtern.</span><span class="sxs-lookup"><span data-stu-id="d7a81-108">PeerChannel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="d7a81-109">Kennwörter können nur verwendet werden, um Zugang zu einer Sitzung zu erhalten. Die Durchführung von Nachrichtenauthentifizierung über Kennwörter ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="d7a81-109">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="d7a81-110">Grund hierfür ist, dass ein symmetrischer Token, den sich eine Peergruppe teilt, für die Quellenauthentifizierung schwierig und ungeeignet ist.</span><span class="sxs-lookup"><span data-stu-id="d7a81-110">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d7a81-111">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="d7a81-111">Troubleshooting</span></span>  
 <span data-ttu-id="d7a81-112">Stellen Sie sicher, dass alle Nachbarn über geeignete Sicherheitsanmeldeinformationen verfügen.</span><span class="sxs-lookup"><span data-stu-id="d7a81-112">Ensure that all neighbors have the appropriate security credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a81-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7a81-113">See Also</span></span>  
 [<span data-ttu-id="d7a81-114">Peerkanalsicherheit</span><span class="sxs-lookup"><span data-stu-id="d7a81-114">Peer Channel Security</span></span>](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)  
 [<span data-ttu-id="d7a81-115">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d7a81-115">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="d7a81-116">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="d7a81-116">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="d7a81-117">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="d7a81-117">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
