---
title: Konfigurieren von Diensten
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: dc3aeadafd54bbd8b57a3e8c781e0cced9e7e632
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="configuring-services"></a>Konfigurieren von Diensten
Nachdem Sie Ihren Dienstvertrag entworfen und implementiert haben, können Sie den Dienst konfigurieren. An diesem Punkt nehmen Sie die Definition und Anpassung vor, wie der Dienst für Clients offengelegt werden soll. Dazu gehört das Angeben der Adresse, unter der der Dienst zugänglich ist, die Transportart und Nachrichtenverschlüsselung, die der Dienst zum Senden und Empfangen von Nachrichten verwendet, sowie der erforderliche Sicherheitstyp.  
  
 Die Konfiguration enthält bei dieser Verwendungsweise alle Möglichkeiten, die Sie zum Definieren und Anpassen der verschiedenen Aspekte eines Diensts verwenden können, ob imperativ im Code oder mithilfe einer Konfigurationsdatei. Dazu gehört auch das Angeben seiner Endpunktadressen, der verwendeten Transportarten und seiner Sicherheitsschemas. In der Praxis ist das Schreiben einer Konfiguration ein wesentlicher Bestandteil beim Programmieren von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Anwendungen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vereinfachte Konfiguration](../../../docs/framework/wcf/simplified-configuration.md)  
 Ab [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)]stellt [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ein neues Standardkonfigurationsmodell bereit, das die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Konfigurationsanforderungen vereinfacht. Wenn Sie keine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Konfiguration für einen bestimmten Dienst bereitstellen, konfiguriert die Runtime den Dienst automatisch mit Standardendpunkten, -bindungen und -verhalten.  
  
 [Konfigurieren von Diensten mit Konfigurationsdateien](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 Ein Windows Communication Foundation (WCF)-Dienst ist konfigurierbar mithilfe der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Konfiguration Technologie. Am häufigsten werden XML-Elemente der Web.config-Datei für eine Internetinformationsdienste (IIS)-Website hinzugefügt, die einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienst hostet. Mithilfe der Elemente können Sie Details ändern, zum Beispiel die Endpunktadressen (die eigentlichen Adressen, die für die Kommunikation mit dem Dienst verwendet werden) für einzelne Computer.  
  
 [Bindungen](../../../docs/framework/wcf/bindings.md)  
 Zusätzlich enthält [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] mehrere vom System bereitgestellte allgemeine Konfigurationen in der Form von Bindungen, mit deren Hilfe Sie schnell die grundlegenden Features für die Kommunikation zwischen Client und Dienst auswählen können, beispielsweise verwendete Transporte, Sicherheit und Nachrichtenverschlüsselungen.  
  
 [Endpunkte](../../../docs/framework/wcf/endpoints.md)  
 Die gesamte Kommunikation mit einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienst verläuft über die *Endpunkte* des Diensts. Endpunkte enthalten den Vertrag, die Konfigurationsinformationen, die in den Bindungen angegeben sind, und die Adressen, die angeben, wo sich der Dienst befindet bzw. wo Informationen zum Dienst verfügbar sind.  
  
 [Sichern von Diensten](../../../docs/framework/wcf/securing-services.md)  
 Indem Sie [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] und vorhandene Sicherheitsmechanismen verwenden, können Sie für jeden Dienst Vertraulichkeit, Integrität, Authentifizierung und Autorisierung implementieren. Sie können auch eine Überprüfung auf Sicherheitserfolge und -misserfolge durchführen.  
  
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
 [Einfache WCF-Programmierung](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [Konzeptionelle Übersicht](../../../docs/framework/wcf/conceptual-overview.md)  
 [Details zur WCF-Funktion](../../../docs/framework/wcf/feature-details/index.md)
