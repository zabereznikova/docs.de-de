---
title: Verbindungsgruppierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Internet, connections
- connections [.NET Framework], grouping
- WebRequest class, connection grouping
- network resources, connections
- connection pooling
ms.assetid: 2ec502e8-4ba0-4c22-9410-f28eaf4eee63
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 924123fcfc441b6a3a41fa29746f00185bff3662
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="connection-grouping"></a><span data-ttu-id="0a0bf-102">Verbindungsgruppierung</span><span class="sxs-lookup"><span data-stu-id="0a0bf-102">Connection Grouping</span></span>
<span data-ttu-id="0a0bf-103">Die Verbindungsgruppierung ordnet bestimmte Anforderungen innerhalb einer einzelnen Anwendung einem definierten Verbindungspool zu.</span><span class="sxs-lookup"><span data-stu-id="0a0bf-103">Connection grouping associates specific requests within a single application to a defined connection pool.</span></span> <span data-ttu-id="0a0bf-104">Dies kann durch eine Anwendung der mittleren Ebene erforderlich sein, die im Auftrag eines Benutzers eine Verbindung mit einem Back-End-Server herstellt und ein Authentifizierungsprotokoll verwendet, das die Delegierung unterstützt, z.B. Kerberos, oder durch eine Anwendung der mittleren Ebene, die, wie im folgenden Beispiel, die eigenen Anmeldeinformationen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0a0bf-104">This can be required by a middle-tier application that connects to a back-end server on behalf of a user and uses an authentication protocol that supports delegation, such as Kerberos, or by a middle-tier application that supplies its own credentials, as in the example below.</span></span> <span data-ttu-id="0a0bf-105">Nehmen wir beispielsweise an, dass ein Benutzer, Joe, eine interne Website besucht, die seine Gehaltsinformationen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="0a0bf-105">For example, suppose a user, Joe, visits an internal Web site that displays his payroll information.</span></span> <span data-ttu-id="0a0bf-106">Nach Joes Authentifizierung verwendet der Server für die Anwendung der mittleren Ebene Joes Anmeldeinformationen für die Verbindung mit dem Back-End-Server, um seine Gehaltsinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0a0bf-106">After authenticating Joe, the middle-tier application server uses Joe's credentials to connect to the back-end server to retrieve his payroll information.</span></span> <span data-ttu-id="0a0bf-107">Anschließend besucht Susan die Website und fordert ihre Gehaltsinformationen an.</span><span class="sxs-lookup"><span data-stu-id="0a0bf-107">Next, Susan visits the site and requests her payroll information.</span></span> <span data-ttu-id="0a0bf-108">Da die Anwendung der mittleren Ebene bereits über eine Verbindung mit Joes Anmeldeinformationen verfügt, gibt der Back-End-Server Joes Informationen zurück.</span><span class="sxs-lookup"><span data-stu-id="0a0bf-108">Because the middle-tier application has already made a connection using Joe's credentials, the back-end server responds with Joe's information.</span></span> <span data-ttu-id="0a0bf-109">Wenn die Anwendung jedoch jede Anforderung an den Back-End-Server einer Verbindungsgruppierung zuweist, die aus dem Benutzernamen gebildet wurde, dann gehört jeder Benutzer zu einem separaten Verbindungspool und kann nicht versehentlich Authentifizierungsinformationen mit einem anderen Benutzer teilen.</span><span class="sxs-lookup"><span data-stu-id="0a0bf-109">However, if the application assigns each request sent to the back-end server to a connection group formed from the user name, then each user belongs to a separate connection pool and cannot accidentally share authentication information with another user.</span></span>  
  
 <span data-ttu-id="0a0bf-110">Sie müssen der <xref:System.Net.WebRequest.ConnectionGroupName%2A>-Eigenschaft Ihrer <xref:System.Net.WebRequest> vor der Anforderung einen Namen zuweisen, um eine Anforderung einer bestimmten Verbindungsgruppe zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0a0bf-110">To assign a request to a specific connection group, you must assign a name to the <xref:System.Net.WebRequest.ConnectionGroupName%2A> property of your <xref:System.Net.WebRequest> before making the request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a0bf-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a0bf-111">See Also</span></span>  
 [<span data-ttu-id="0a0bf-112">Verwalten von Verbindungen</span><span class="sxs-lookup"><span data-stu-id="0a0bf-112">Managing Connections</span></span>](../../../docs/framework/network-programming/managing-connections.md)  
 [<span data-ttu-id="0a0bf-113">Vorgehensweise: Zuweisen von Benutzerinformationen zu Gruppenverbindungen</span><span class="sxs-lookup"><span data-stu-id="0a0bf-113">How to: Assign User Information to Group Connections</span></span>](../../../docs/framework/network-programming/how-to-assign-user-information-to-group-connections.md)
