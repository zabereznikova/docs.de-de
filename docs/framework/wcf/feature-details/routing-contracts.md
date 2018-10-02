---
title: Routingverträge
ms.date: 03/30/2017
ms.assetid: 9ceea7ae-ea19-4cf9-ba4f-d071e236546d
ms.openlocfilehash: 73d303c95a636f5e90f256272726c08c581d6fdf
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48046343"
---
# <a name="routing-contracts"></a>Routingverträge
Routingverträge definieren die Nachrichtenmuster, die der Routingdienst verarbeiten kann.  Jeder Vertrag ist typenlos und ermöglicht es dem Dienst, eine Nachricht ohne Kenntnis des Nachrichtenschemas oder der Nachrichtenaktion zu empfangen. Auf diese Weise kann der Routingdienst Nachrichten generisch weiterleiten, ohne dass eine zusätzliche Konfiguration für die Einzelheiten der zugrunde liegenden weitergeleiteten Nachrichten erforderlich ist.  
  
## <a name="routing-contracts"></a>Routingverträge  
 Da der Routingdienst ein generisches WCF-Nachrichtenobjekt akzeptiert, ist der wichtigste Aspekt bei der Auswahl eines Vertrags die Form des Kanals, der für die Kommunikation mit den Clients und Diensten verwendet wird. Beim Verarbeiten von Nachrichten verwendet der Routingdienst symmetrische Nachrichtensysteme. Die Form des eingehenden Vertrags muss im Allgemeinen also der Form des ausgehenden Vertrags entsprechen. Es gibt jedoch Fälle, in dem durch den Verteiler des Dienstmodells die Formen, wie z. B. wenn der Verteiler einen Duplexkanal in einen Anforderung-Antwort-Kanal konvertiert oder die sitzungsunterstützung aus einem Kanal entfernt wird, wird (d. h. nicht verwendet und ist nicht erforderlich, ändern können Wenn **SessionMode.Allowed**konvertiert eine **IInputSessionChannel** in einer **IInputChannel**).  
  
 Zur Unterstützung dieser Nachrichtensysteme stellt der Routingdienst Verträge im <xref:System.ServiceModel.Routing>-Namespace bereit, die verwendet werden müssen, wenn vom Routingdienst genutzte Dienstendpunkte definiert werden. Diese Verträge sind typenlos, sodass jede Art von Nachrichtentyp oder -aktion empfangen werden kann. Außerdem kann der Routingdienst so Nachrichten ohne Kenntnis des jeweiligen Nachrichtenschemas behandeln. Weitere Informationen zu den Verträgen, die vom Routingdienst verwendet, finden Sie unter [Routing Verträge](../../../../docs/framework/wcf/feature-details/routing-contracts.md).  
  
 Die vom Routingdienst bereitgestellten Verträge befinden sich im <xref:System.ServiceModel.Routing>-Namespace und sind in der folgenden Tabelle beschrieben.  
  
|Vertrag|Form|Kanalform|  
|--------------|-----------|-------------------|  
|<xref:System.ServiceModel.Routing.ISimplexDatagramRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputChannel -> IOutputChannel|  
|<xref:System.ServiceModel.Routing.ISimplexSessionRouter>|SessionMode = SessionMode.Required<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputSessionChannel -> IOutputSessionChannel|  
|<xref:System.ServiceModel.Routing.IRequestReplyRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true|IReplyChannel -> IRequestChannel|  
|<xref:System.ServiceModel.Routing.IDuplexSessionRouter>|SessionMode=SessionMode.Required<br /><br /> CallbackContract=typeof(ISimplexSession)<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true<br /><br /> TransactionFlow(TransactionFlowOption.Allowed)|IDuplexSessionChannel -> IDuplexSessionChannel|  
  
## <a name="see-also"></a>Siehe auch  
 [Routingdienst](https://msdn.microsoft.com/library/5ac8718c-bcef-456f-bfd5-1e60a30d6eaa)  
 [Einführung in Routing](../../../../docs/framework/wcf/feature-details/routing-introduction.md)
