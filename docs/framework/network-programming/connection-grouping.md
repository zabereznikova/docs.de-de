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
ms.openlocfilehash: 007366764a7b8e1208e22ef5895e6a9093b090e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048647"
---
# <a name="connection-grouping"></a>Verbindungsgruppierung
Die Verbindungsgruppierung ordnet bestimmte Anforderungen innerhalb einer einzelnen Anwendung einem definierten Verbindungspool zu. Dies kann durch eine Anwendung der mittleren Ebene erforderlich sein, die im Auftrag eines Benutzers eine Verbindung mit einem Back-End-Server herstellt und ein Authentifizierungsprotokoll verwendet, das die Delegierung unterstützt, z.B. Kerberos, oder durch eine Anwendung der mittleren Ebene, die, wie im folgenden Beispiel, die eigenen Anmeldeinformationen bereitstellt. Nehmen wir beispielsweise an, dass ein Benutzer, Joe, eine interne Website besucht, die seine Gehaltsinformationen anzeigt. Nach Joes Authentifizierung verwendet der Server für die Anwendung der mittleren Ebene Joes Anmeldeinformationen für die Verbindung mit dem Back-End-Server, um seine Gehaltsinformationen abzurufen. Anschließend besucht Susan die Website und fordert ihre Gehaltsinformationen an. Da die Anwendung der mittleren Ebene bereits über eine Verbindung mit Joes Anmeldeinformationen verfügt, gibt der Back-End-Server Joes Informationen zurück. Wenn die Anwendung jedoch jede Anforderung an den Back-End-Server einer Verbindungsgruppierung zuweist, die aus dem Benutzernamen gebildet wurde, dann gehört jeder Benutzer zu einem separaten Verbindungspool und kann nicht versehentlich Authentifizierungsinformationen mit einem anderen Benutzer teilen.  
  
 Sie müssen der <xref:System.Net.WebRequest.ConnectionGroupName%2A>-Eigenschaft Ihrer <xref:System.Net.WebRequest> vor der Anforderung einen Namen zuweisen, um eine Anforderung einer bestimmten Verbindungsgruppe zuzuweisen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwalten von Verbindungen](managing-connections.md)
- [Vorgehensweise: Zuweisen von Benutzerinformationen zu Gruppenverbindungen](how-to-assign-user-information-to-group-connections.md)
