---
title: Wiederholungsangriffe
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a17e040-93cd-4432-81b9-9f62fec78c8f
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4e827c51378b9f75835b9b98280b4995d2cae2fc
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="replay-attacks"></a><span data-ttu-id="6aa7b-102">Wiederholungsangriffe</span><span class="sxs-lookup"><span data-stu-id="6aa7b-102">Replay Attacks</span></span>
<span data-ttu-id="6aa7b-103">Ein *Wiederholungsangriff* tritt auf, wenn ein Angreifer einen Nachrichtenstream zwischen zwei Parteien kopiert und den Strom für eine oder mehrere Parteien wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-103">A *replay attack* occurs when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties.</span></span> <span data-ttu-id="6aa7b-104">Wenn der Angriff nicht abgeschwächt wird, verarbeiten die angegriffenen Computer den Stream wie zulässige Nachrichten, was eine Reihe negativer Konsequenzen wie redundante Bestellungen eines Artikels zur Folge hat.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-104">Unless mitigated, the computers subject to the attack process the stream as legitimate messages, resulting in a range of bad consequences, such as redundant orders of an item.</span></span>  
  
## <a name="bindings-may-be-subject-to-reflection-attacks"></a><span data-ttu-id="6aa7b-105">Bindungen sind möglicherweise Reflektionsangriffen ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="6aa7b-105">Bindings May Be Subject to Reflection Attacks</span></span>  
 <span data-ttu-id="6aa7b-106">*Reflektionsangriffe* Replays von Nachrichten an einen Sender sind, als ob sie vom Empfänger der Antwort geliefert wurde.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-106">*Reflection attacks* are replays of messages back to a sender as if they came from the receiver as the reply.</span></span> <span data-ttu-id="6aa7b-107">Der Standard *replay-Erkennung* in die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Mechanismus wird nicht automatisch behandelt.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-107">The standard *replay detection* in the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] mechanism does not automatically handle this.</span></span>  
  
 <span data-ttu-id="6aa7b-108">Reflektionsangriffe werden standardmäßig abgeschwächt, da das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstmodell Anforderungsnachrichten eine signierte Nachrichtenkennung hinzufügt und in Antwortnachrichten einen signierten `relates-to`-Header erwartet.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-108">Reflection attacks are mitigated by default because the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service model adds a signed message ID to request messages and expects a signed `relates-to` header on response messages.</span></span> <span data-ttu-id="6aa7b-109">Infolgedessen kann die Anforderungsnachricht nicht als Antwort wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-109">Consequently, the request message cannot be replayed as a response.</span></span> <span data-ttu-id="6aa7b-110">In sicheren Szenarien mit zuverlässigem Messaging werden Reflektionsangriffe aus folgenden Gründen abgemildert:</span><span class="sxs-lookup"><span data-stu-id="6aa7b-110">In secure reliable message (RM) scenarios, reflection attacks are mitigated because:</span></span>  
  
-   <span data-ttu-id="6aa7b-111">Die Sequenzerstellung und die Sequenzerstellungsantwort verwenden unterschiedliche Nachrichtenschemas.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-111">The create sequence and create sequence response message schemas are different.</span></span>  
  
-   <span data-ttu-id="6aa7b-112">Bei Simplexsequenzen können die vom Client gesendeten Nachrichten nicht wiedergegeben werden, da diese vom Client nicht interpretiert werden können.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-112">For simplex sequences, sequence messages the client sends cannot be replayed back to it because the client cannot understand such messages.</span></span>  
  
-   <span data-ttu-id="6aa7b-113">Bei Duplexsequenzen müssen die beiden Sequenzkennungen eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-113">For duplex sequences, the two sequence IDs must be unique.</span></span> <span data-ttu-id="6aa7b-114">Ausgehende Nachrichten können daher nicht als eingehende Nachrichten wiederholt werden (alle Header und Texte werden ebenfalls signiert).</span><span class="sxs-lookup"><span data-stu-id="6aa7b-114">Thus, an outgoing sequence message cannot be replayed back as an incoming sequence message (all sequence headers and bodies are signed, too).</span></span>  
  
 <span data-ttu-id="6aa7b-115">Aus diesem Grund sind nur Bindungen ohne WS-Adressierung anfällig für Reflektionsangriffe: benutzerdefinierte Bindungen, deren WS-Adressierung deaktiviert ist und die mit symmetrischen Schlüsseln gesichert sind.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-115">The only bindings that are susceptible to reflection attacks are those without WS-Addressing: custom bindings that have WS-Addressing disabled and use the symmetric key-based security.</span></span> <span data-ttu-id="6aa7b-116">Die <xref:System.ServiceModel.BasicHttpBinding> verwendet standardmäßig keine WS-Adressierung; die Absicherung durch symmetrische Schlüssel erfolgt jedoch auf eine Art und Weise, die sie anfällig gegenüber dieser Art von Angriffen macht.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-116">The <xref:System.ServiceModel.BasicHttpBinding> does not use WS-Addressing by default, but it does not use symmetric key-based security in a way that allows it to be vulnerable to this attack.</span></span>  
  
 <span data-ttu-id="6aa7b-117">Zur Entschärfung für benutzerdefinierte Bindungen sollte auf einen Sicherheitskontext verzichtet werden, oder es sollten Header für die WS-Adressierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-117">The mitigation for custom bindings is to not establish security context or to require WS-Addressing headers.</span></span>  
  
## <a name="web-farm-attacker-replays-request-to-multiple-nodes"></a><span data-ttu-id="6aa7b-118">Webfarm: Angriff durch Wiederholen von Anforderungen an mehrere Knoten</span><span class="sxs-lookup"><span data-stu-id="6aa7b-118">Web Farm: Attacker Replays Request to Multiple Nodes</span></span>  
 <span data-ttu-id="6aa7b-119">Ein Client verwendet einen Dienst, der in einer Webfarm implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-119">A client uses a service that is implemented on a Web farm.</span></span> <span data-ttu-id="6aa7b-120">Ein Angreifer wiederholt eine Anforderung, die an einen Knoten in der Farm gesendet wurde, für einen anderen Knoten in der Farm.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-120">An attacker replays a request that was sent to one node in the farm to another node in the farm.</span></span> <span data-ttu-id="6aa7b-121">Zusätzlich wird beim Neustart eines Diensts der Wiederholungscache geleert, sodass der Angriff wiederholt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-121">In addition, if a service is restarted, the replay cache is flushed, allowing an attacker to replay the request.</span></span> <span data-ttu-id="6aa7b-122">(Der Cache enthält die bereits verwendeten Signaturen von Nachrichten und verhindert so, dass diese mehrfach verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-122">(The cache contains used, previously seen message signature values and prevents replays so those signatures can be used only once.</span></span> <span data-ttu-id="6aa7b-123">Wiederholungscaches werden nicht von mehreren Anwendungen in einer Webfarm verwendet.)</span><span class="sxs-lookup"><span data-stu-id="6aa7b-123">Replay caches are not shared across a Web farm.)</span></span>  
  
 <span data-ttu-id="6aa7b-124">Mögliche Gegenmaßnahmen:</span><span class="sxs-lookup"><span data-stu-id="6aa7b-124">Mitigations include:</span></span>  
  
-   <span data-ttu-id="6aa7b-125">Verwenden Sie die Nachrichtenmodussicherheit mit zustandsbehafteten Token für den Sicherheitskontext (mit oder ohne sichere Konversation).</span><span class="sxs-lookup"><span data-stu-id="6aa7b-125">Use message mode security with stateful security context tokens (with or without secure conversation enabled).</span></span> <span data-ttu-id="6aa7b-126">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie ein Sicherheitskontexttoken für eine Sicherheitssitzung](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span><span class="sxs-lookup"><span data-stu-id="6aa7b-126">For more information, see [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
-   <span data-ttu-id="6aa7b-127">Konfigurieren Sie den Dienst für die Sicherheit auf Transportebene.</span><span class="sxs-lookup"><span data-stu-id="6aa7b-127">Configure the service to use transport-level security.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa7b-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6aa7b-128">See Also</span></span>  
 [<span data-ttu-id="6aa7b-129">Sicherheitsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="6aa7b-129">Security Considerations</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [<span data-ttu-id="6aa7b-130">Offenlegung vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="6aa7b-130">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 [<span data-ttu-id="6aa7b-131">Erhöhen der Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6aa7b-131">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [<span data-ttu-id="6aa7b-132">Denial-of-Service-Angriffe</span><span class="sxs-lookup"><span data-stu-id="6aa7b-132">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [<span data-ttu-id="6aa7b-133">Manipulation</span><span class="sxs-lookup"><span data-stu-id="6aa7b-133">Tampering</span></span>](../../../../docs/framework/wcf/feature-details/tampering.md)  
 [<span data-ttu-id="6aa7b-134">Nicht unterstützte Szenarien</span><span class="sxs-lookup"><span data-stu-id="6aa7b-134">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
