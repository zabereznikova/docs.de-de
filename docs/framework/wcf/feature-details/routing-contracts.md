---
title: Routingverträge
ms.date: 03/30/2017
ms.assetid: 9ceea7ae-ea19-4cf9-ba4f-d071e236546d
ms.openlocfilehash: 4c75034a8fdbf02bf568bc5392361113a37427be
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295495"
---
# <a name="routing-contracts"></a>Routingverträge

Routingverträge definieren die Nachrichtenmuster, die der Routingdienst verarbeiten kann.  Jeder Vertrag ist typenlos und ermöglicht es dem Dienst, eine Nachricht ohne Kenntnis des Nachrichtenschemas oder der Nachrichtenaktion zu empfangen. Auf diese Weise kann der Routingdienst Nachrichten generisch weiterleiten, ohne dass eine zusätzliche Konfiguration für die Einzelheiten der zugrunde liegenden weitergeleiteten Nachrichten erforderlich ist.  
  
## <a name="routing-contracts"></a>Routingverträge  

 Da der Routingdienst ein generisches WCF-Nachrichtenobjekt akzeptiert, ist der wichtigste Aspekt bei der Auswahl eines Vertrags die Form des Kanals, der für die Kommunikation mit den Clients und Diensten verwendet wird. Beim Verarbeiten von Nachrichten verwendet der Routingdienst symmetrische Nachrichtensysteme. Die Form des eingehenden Vertrags muss im Allgemeinen also der Form des ausgehenden Vertrags entsprechen. Allerdings es gibt Fälle, in denen der Verteiler des Dienst Modells die Formen ändern kann, z. b. wenn der Verteiler einen Duplex Kanal in einen Anforderungs-/Antwort-Channel konvertiert oder die Sitzungsunterstützung von einem Kanal entfernt, wenn dies nicht erforderlich ist und nicht verwendet wird (d. h., wenn " **SessionMode. Allowed** **" in einen** **IInputChannel** konvertiert wird).  
  
 Zur Unterstützung dieser Nachrichtensysteme stellt der Routingdienst Verträge im <xref:System.ServiceModel.Routing>-Namespace bereit, die verwendet werden müssen, wenn vom Routingdienst genutzte Dienstendpunkte definiert werden. Diese Verträge sind typenlos, sodass jede Art von Nachrichtentyp oder -aktion empfangen werden kann. Außerdem kann der Routingdienst so Nachrichten ohne Kenntnis des jeweiligen Nachrichtenschemas behandeln. Weitere Informationen zu den vom Routing Dienst verwendeten Verträgen finden Sie unter [Routing Verträge](routing-contracts.md).  
  
 Die vom Routingdienst bereitgestellten Verträge befinden sich im <xref:System.ServiceModel.Routing>-Namespace und sind in der folgenden Tabelle beschrieben.  
  
|Vertrag|Form|Kanalform|  
|--------------|-----------|-------------------|  
|<xref:System.ServiceModel.Routing.ISimplexDatagramRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputChannel-> IOutputChannel|  
|<xref:System.ServiceModel.Routing.ISimplexSessionRouter>|SessionMode = SessionMode.Required<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputSessionChannel-> IOutputSessionChannel|  
|<xref:System.ServiceModel.Routing.IRequestReplyRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true|IReplyChannel-> IRequestChannel|  
|<xref:System.ServiceModel.Routing.IDuplexSessionRouter>|SessionMode=SessionMode.Required<br /><br /> CallbackContract=typeof(ISimplexSession)<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true<br /><br /> TransactionFlow(TransactionFlowOption.Allowed)|IDuplexSessionChannel-> IDuplexSessionChannel|  
  
## <a name="see-also"></a>Weitere Informationen

- [Routingdienst](routing-service.md)
- [Einführung in das Routing](routing-introduction.md)
