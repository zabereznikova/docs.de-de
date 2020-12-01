---
title: PNRP in der Anwendungsentwicklung
ms.date: 03/30/2017
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
ms.openlocfilehash: 7c59b2be8384c8f8cc6bbdc4546a678cfe1c538d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263190"
---
# <a name="pnrp-in-application-development"></a>PNRP in der Anwendungsentwicklung

In Windows Vista können Netzwerkanwendungen über eine vereinfachte PNRP-Anwendungsprogrammierschnittstelle (application programming interface – API) auf Funktionen zur Veröffentlichung und Auflösung von Namen zugreifen.  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a>Implementieren des Peer Name Resolution-Protokolls  

 Bei der vereinfachten PNRP-API werden Clouds nicht explizit für die Namens- und Adressregistrierung angegeben. Die PNRP-Komponente bestimmt automatisch, welchen passenden Clouds beigetreten werden soll und welche Adressen in diesen veröffentlicht werden sollen.  
  
 Für die sehr stark vereinfachte PNRP-Namensauflösung in Windows Vista werden PNRP-Namen nun in die Windows Sockets-Funktion getaddrinfo() integriert. Namen lassen sich mithilfe von PNRP in eine IPv6-Adresse aufzulösen. Dazu können Anwendungen mit der Funktion getaddrinfo() den vollqualifizierten Domänennamen (Fully Qualified Domain Name – FQDN) „name-prnp.net“ verwenden. „name“ steht hier für den aufzulösenden Peernamen. Die Domain „pnrp.net“ ist in Windows Vista für die Auflösung von PNRP-Namen reserviert.  
  
 Die Nachrichtenübergabe zwischen Peer-zu-Peer-Anwendungen wird weiterhin von der zu Grunde liegenden Architektur übernommen, z.B. PeerChannel oder der WCF-Funktion für [umfangreiche Daten und Streaming](../wcf/feature-details/large-data-and-streaming.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.PeerToPeer>
