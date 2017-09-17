---
title: Verbindungsgruppierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Internet, connections
- connections [.NET Framework], grouping
- WebRequest class, connection grouping
- network resources, connections
- connection pooling
ms.assetid: 2ec502e8-4ba0-4c22-9410-f28eaf4eee63
caps.latest.revision: 7
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8f16a539bb7c2bef494c7b5551e1f12bc71de60f
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="connection-grouping"></a>Verbindungsgruppierung
Die Verbindungsgruppierung ordnet bestimmte Anforderungen innerhalb einer einzelnen Anwendung einem definierten Verbindungspool zu. Dies kann durch eine Anwendung der mittleren Ebene erforderlich sein, die im Auftrag eines Benutzers eine Verbindung mit einem Back-End-Server herstellt und ein Authentifizierungsprotokoll verwendet, das die Delegierung unterstützt, z.B. Kerberos, oder durch eine Anwendung der mittleren Ebene, die, wie im folgenden Beispiel, die eigenen Anmeldeinformationen bereitstellt. Nehmen wir beispielsweise an, dass ein Benutzer, Joe, eine interne Website besucht, die seine Gehaltsinformationen anzeigt. Nach Joes Authentifizierung verwendet der Server für die Anwendung der mittleren Ebene Joes Anmeldeinformationen für die Verbindung mit dem Back-End-Server, um seine Gehaltsinformationen abzurufen. Anschließend besucht Susan die Website und fordert ihre Gehaltsinformationen an. Da die Anwendung der mittleren Ebene bereits über eine Verbindung mit Joes Anmeldeinformationen verfügt, gibt der Back-End-Server Joes Informationen zurück. Wenn die Anwendung jedoch jede Anforderung an den Back-End-Server einer Verbindungsgruppierung zuweist, die aus dem Benutzernamen gebildet wurde, dann gehört jeder Benutzer zu einem separaten Verbindungspool und kann nicht versehentlich Authentifizierungsinformationen mit einem anderen Benutzer teilen.  
  
 Sie müssen der <xref:System.Net.WebRequest.ConnectionGroupName%2A>-Eigenschaft Ihrer <xref:System.Net.WebRequest> vor der Anforderung einen Namen zuweisen, um eine Anforderung einer bestimmten Verbindungsgruppe zuzuweisen.  
  
## <a name="see-also"></a>Siehe auch  
 [Managing Connections (Verwalten von Verbindungen)](../../../docs/framework/network-programming/managing-connections.md)   
 [Vorgehensweise: Zuweisen von Benutzerinformationen zu Gruppenverbindungen](../../../docs/framework/network-programming/how-to-assign-user-information-to-group-connections.md)

