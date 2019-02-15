---
title: Konfigurieren von WCF-Diensten
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: 2435d5c4592de60e07b60f1bf749f2421c798535
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303604"
---
# <a name="configuring-wcf-services"></a>Konfigurieren von WCF-Diensten

Nachdem Sie Ihren Dienstvertrag entworfen und implementiert haben, können Sie den Dienst konfigurieren. An diesem Punkt nehmen Sie die Definition und Anpassung vor, wie der Dienst für Clients offengelegt werden soll. Dazu gehört das Angeben der Adresse, unter der der Dienst zugänglich ist, die Transportart und Nachrichtenverschlüsselung, die der Dienst zum Senden und Empfangen von Nachrichten verwendet, sowie der erforderliche Sicherheitstyp.  
  
 Die Konfiguration enthält bei dieser Verwendungsweise alle Möglichkeiten, die Sie zum Definieren und Anpassen der verschiedenen Aspekte eines Diensts verwenden können, ob imperativ im Code oder mithilfe einer Konfigurationsdatei. Dazu gehört auch das Angeben seiner Endpunktadressen, der verwendeten Transportarten und seiner Sicherheitsschemas. In der Praxis ist das Schreiben einer Konfiguration einem wesentlichen Teil der WCF-Anwendungen zu programmieren.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vereinfachte Konfiguration](../../../docs/framework/wcf/simplified-configuration.md)  
 Beginnend mit [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF enthält ein neues Standard-Konfigurationsmodell, das WCF-konfigurationsanforderungen vereinfacht. Wenn Sie keine WCF-Konfiguration für einen bestimmten Dienst bereitstellen, konfiguriert die Runtime automatisch Ihren Dienst mit Standardendpunkten, Bindungen und Verhaltensweisen.  
  
 [Konfigurieren von Diensten mit Konfigurationsdateien](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 Ein Windows Communication Foundation (WCF)-Dienst ist konfigurierbar mit der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Configuration-Technologie. In den meisten Fällen werden die XML-Elemente in die Datei "Web.config" für eine Website (Internet Information Services, IIS) hinzugefügt, die einen WCF-Dienst hostet. Mithilfe der Elemente können Sie Details ändern, zum Beispiel die Endpunktadressen (die eigentlichen Adressen, die für die Kommunikation mit dem Dienst verwendet werden) für einzelne Computer.  
  
 [Bindungen](../../../docs/framework/wcf/bindings.md)  
 Darüber hinaus werden WCF mehrere vom System bereitgestellte Allgemeine Konfigurationen in Form von Bindungen, mit denen Sie schnell auswählen, die die grundlegenden Features für die Kommunikation Client und Dienst zwischen, z. B. die Transporte, Sicherheit und Codierungen verwendet.  
  
 [Endpunkte](../../../docs/framework/wcf/endpoints.md)  
 Die gesamte Kommunikation mit einem WCF-Dienst erfolgt über die *Endpunkte* des Diensts. Endpunkte enthalten den Vertrag, die Konfigurationsinformationen, die in den Bindungen angegeben sind, und die Adressen, die angeben, wo sich der Dienst befindet bzw. wo Informationen zum Dienst verfügbar sind.  
  
 [Sichern von Diensten](../../../docs/framework/wcf/securing-services.md)  
 Verwenden von WCF und vorhandene Sicherheitsmechanismen, Sie können die Vertraulichkeit, Integrität, Authentifizierung und Autorisierung in jeden Dienst implementieren. Sie können auch eine Überprüfung auf Sicherheitserfolge und -misserfolge durchführen.  
  
 [Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 Die Anforderungen zum Verwenden eines Dienstes, der über die Interoperabilität mit Diensten und Clients auf beliebigen anderen Plattformen oder Betriebssystemen verfügt, sind in der WS-I Basic Profile 1.1-Spezifikation beschrieben.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Grundlegender Programmierlebenszyklus](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [Entwerfen und Implementieren von Diensten](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [Hosting-Dienste](../../../docs/framework/wcf/hosting-services.md)  
  
 [Erstellen von Clients](../../../docs/framework/wcf/building-clients.md)  
  
 [Einführung in die Erweiterbarkeit](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [Verwaltung und Diagnose](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a>Siehe auch
- [Einfache WCF-Programmierung](../../../docs/framework/wcf/basic-wcf-programming.md)
- [Konzeptionelle Übersicht](../../../docs/framework/wcf/conceptual-overview.md)
- [Details zur WCF-Funktion](../../../docs/framework/wcf/feature-details/index.md)
