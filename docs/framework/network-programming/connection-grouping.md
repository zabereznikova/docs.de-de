---
title: Verbindungsgruppierung
ms.date: 03/30/2017
helpviewer_keywords:
- Internet, connections
- connections [.NET Framework], grouping
- WebRequest class, connection grouping
- network resources, connections
- connection pooling
ms.assetid: 2ec502e8-4ba0-4c22-9410-f28eaf4eee63
ms.openlocfilehash: 28d8771b4535c20a2b65fc8dbbe45407eb041a34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658064"
---
# <a name="connection-grouping"></a>Verbindungsgruppierung
Die Verbindungsgruppierung ordnet bestimmte Anforderungen innerhalb einer einzelnen Anwendung einem definierten Verbindungspool zu. Dies kann durch eine Anwendung der mittleren Ebene erforderlich sein, die im Auftrag eines Benutzers eine Verbindung mit einem Back-End-Server herstellt und ein Authentifizierungsprotokoll verwendet, das die Delegierung unterstützt, z.B. Kerberos, oder durch eine Anwendung der mittleren Ebene, die, wie im folgenden Beispiel, die eigenen Anmeldeinformationen bereitstellt. Nehmen wir beispielsweise an, dass ein Benutzer, Joe, eine interne Website besucht, die seine Gehaltsinformationen anzeigt. Nach Joes Authentifizierung verwendet der Server für die Anwendung der mittleren Ebene Joes Anmeldeinformationen für die Verbindung mit dem Back-End-Server, um seine Gehaltsinformationen abzurufen. Anschließend besucht Susan die Website und fordert ihre Gehaltsinformationen an. Da die Anwendung der mittleren Ebene bereits über eine Verbindung mit Joes Anmeldeinformationen verfügt, gibt der Back-End-Server Joes Informationen zurück. Wenn die Anwendung jedoch jede Anforderung an den Back-End-Server einer Verbindungsgruppierung zuweist, die aus dem Benutzernamen gebildet wurde, dann gehört jeder Benutzer zu einem separaten Verbindungspool und kann nicht versehentlich Authentifizierungsinformationen mit einem anderen Benutzer teilen.  
  
 Sie müssen der <xref:System.Net.WebRequest.ConnectionGroupName%2A>-Eigenschaft Ihrer <xref:System.Net.WebRequest> vor der Anforderung einen Namen zuweisen, um eine Anforderung einer bestimmten Verbindungsgruppe zuzuweisen.  
  
## <a name="see-also"></a>Siehe auch
- [Verwalten von Verbindungen](../../../docs/framework/network-programming/managing-connections.md)
- [Vorgehensweise: Zuweisen von Benutzerinformationen an Gruppenverbindungen](../../../docs/framework/network-programming/how-to-assign-user-information-to-group-connections.md)
