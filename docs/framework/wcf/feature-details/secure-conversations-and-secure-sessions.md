---
title: Sichere Unterhaltungen und sichere Sitzungen.
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
caps.latest.revision: 13
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 502064ce30f6e117168834643a116d3983811fb8
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="secure-conversations-and-secure-sessions"></a><span data-ttu-id="e948a-102">Sichere Unterhaltungen und sichere Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="e948a-102">Secure Conversations and Secure Sessions</span></span>
<span data-ttu-id="e948a-103">Eine Funktion von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ist die Fähigkeit, sichere Sitzungen zwischen zwei Endpunkten aufzubauen, die sich gegenseitig authentifizieren und sich auf ein Verfahren zur Verschlüsselung und digitalen Signatur einigen.</span><span class="sxs-lookup"><span data-stu-id="e948a-103">A feature of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is the ability to establish secure sessions between two endpoints that authenticate each other and agree upon an encryption and digital signature process.</span></span> <span data-ttu-id="e948a-104">Der Dienstendpunkt könnte beispielsweise einen Clientendpunkt benötigen, um zur Authentifizierung ein Sicherheitstoken zu senden, das auf einem X.509-Zertifikat basiert.</span><span class="sxs-lookup"><span data-stu-id="e948a-104">For example, the service endpoint might require a client endpoint to send a security token based upon an X.509 certificate for authentication.</span></span> <span data-ttu-id="e948a-105">Sobald der Client authentifiziert ist, gibt der Dienstendpunkt ein Sicherheitskontexttoken (SCT) an den Client zurück, das dann verwendet wird, um alle folgenden Nachrichten innerhalb der Sitzung zu sichern.</span><span class="sxs-lookup"><span data-stu-id="e948a-105">Once the client is authenticated, the service endpoint returns a security context token (SCT) back to the client that is then used to secure all subsequent messages within the session.</span></span> <span data-ttu-id="e948a-106">Durch das Einrichten dieser sicheren Sitzung kann der Nachrichtensatz, der zwischen den beiden Endpunkten ausgetauscht wird, effizienter werden, da SCT über einen symmetrischen Schlüssel verfügt.</span><span class="sxs-lookup"><span data-stu-id="e948a-106">Establishing this secure session enables the set of messages that are exchanged between the two endpoints to be more efficient, because the SCT has a symmetric key.</span></span> <span data-ttu-id="e948a-107">In Bezug auf das Generieren einer digitalen Signatur oder Verschlüsseln eines Datensatzes erfordern asymmetrische Schlüssel, auf denen X.509-Zertifikate basieren, bedeutend mehr Rechenleistung als symmetrische Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="e948a-107">Asymmetric keys, which X.509 certificates are based upon, require significantly more computational power than symmetric keys when generating a digital signature or encrypting a set of data.</span></span>  
  
 <span data-ttu-id="e948a-108">Die bootstrap-Richtlinie (im Abschnitt 6.2.7 definiert die [WS-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817) standard) die Nachricht Sicherheit Assertionen verwendet, um den Kanal sichern und Authentifizieren des Clients vor der RST/SCT und RSTR/SCT-Austausch enthält.</span><span class="sxs-lookup"><span data-stu-id="e948a-108">The bootstrap policy (defined in section 6.2.7 of the [WS-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817) standard) contains the message security assertions used to secure the channel and authenticate the client prior to the RST/SCT and RSTR/SCT exchange.</span></span> <span data-ttu-id="e948a-109">Bestimmte [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Standardbindungen verfügen über eine `Security.Message.EstablishSecurityContext`-Eigenschaft, welche steuert, ob eine sichere Konversation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e948a-109">Certain [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] standard bindings have a `Security.Message.EstablishSecurityContext` property which controls whether secure conversation is used.</span></span> <span data-ttu-id="e948a-110">Bei Verwendung von benutzerdefinierten Bindungen sind Bootstrapper durch Schachteln Sicherheitsbindungselemente entweder durch [ \<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) in der Konfigurationsdatei oder durch Aufrufen von <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> im Code.</span><span class="sxs-lookup"><span data-stu-id="e948a-110">When using custom bindings the bootstrap is indicated by nesting security binding elements, either through [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) in the configuration file, or by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> in code.</span></span>  
  
 <span data-ttu-id="e948a-111">Weitere Informationen zu Sitzungen finden Sie unter [mit Sitzungen](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="e948a-111">For more information about sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e948a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e948a-112">See Also</span></span>  
 [<span data-ttu-id="e948a-113">Sitzungen, Instanzerstellung und Parallelität</span><span class="sxs-lookup"><span data-stu-id="e948a-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [<span data-ttu-id="e948a-114">Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert</span><span class="sxs-lookup"><span data-stu-id="e948a-114">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
