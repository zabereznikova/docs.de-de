---
title: Konfigurieren von WCF-Diensten
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: a5fe0cabb1a6be7f93bf5f4d753e9bb08a39cea3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253335"
---
# <a name="configuring-wcf-services"></a>Konfigurieren von WCF-Diensten

Nachdem Sie Ihren Dienstvertrag entworfen und implementiert haben, können Sie den Dienst konfigurieren. An diesem Punkt nehmen Sie die Definition und Anpassung vor, wie der Dienst für Clients offengelegt werden soll. Dazu gehört das Angeben der Adresse, unter der der Dienst zugänglich ist, die Transportart und Nachrichtenverschlüsselung, die der Dienst zum Senden und Empfangen von Nachrichten verwendet, sowie der erforderliche Sicherheitstyp.  
  
 Die Konfiguration enthält bei dieser Verwendungsweise alle Möglichkeiten, die Sie zum Definieren und Anpassen der verschiedenen Aspekte eines Diensts verwenden können, ob imperativ im Code oder mithilfe einer Konfigurationsdatei. Dazu gehört auch das Angeben seiner Endpunktadressen, der verwendeten Transportarten und seiner Sicherheitsschemas. In der Praxis ist das Schreiben von Konfigurationen ein wesentlicher Bestandteil der Programmierung von WCF-Anwendungen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Vereinfachte Konfiguration](simplified-configuration.md)  
 Ab .NET Framework 4 enthält WCF ein neues Standard Konfigurations Modell, das die WCF-Konfigurations Anforderungen vereinfacht. Wenn Sie keine WCF-Konfiguration für einen bestimmten Dienst bereitstellen, konfiguriert die Runtime den Dienst automatisch mit Standard Endpunkten, Bindungen und Verhaltensweisen.  
  
 [Konfigurieren von Diensten mit Konfigurationsdateien](configuring-services-using-configuration-files.md)  
 Ein Windows Communication Foundation (WCF)-Dienst kann mit der .NET Framework-Konfigurations Technologie konfiguriert werden. In den meisten Fällen werden der Web.config Datei für eine Internetinformationsdienste (IIS)-Website, die einen WCF-Dienst hostet, XML-Elemente hinzugefügt. Mithilfe der Elemente können Sie Details ändern, zum Beispiel die Endpunktadressen (die eigentlichen Adressen, die für die Kommunikation mit dem Dienst verwendet werden) für einzelne Computer.  
  
 [Bindungen](bindings.md)  
 Außerdem umfasst WCF mehrere vom System bereitgestellte allgemeine Konfigurationen in Form von Bindungen, mit denen Sie schnell die grundlegendsten Features für die Kommunikation zwischen Client und Dienst auswählen können, wie z. b. die verwendeten Transporte, Sicherheit und Nachrichten Codierungen.  
  
 [Endpunkte](endpoints.md)  
 Die gesamte Kommunikation mit einem WCF-Dienst erfolgt über die *Endpunkte* des Dienstanbieter. Endpunkte enthalten den Vertrag, die Konfigurationsinformationen, die in den Bindungen angegeben sind, und die Adressen, die angeben, wo sich der Dienst befindet bzw. wo Informationen zum Dienst verfügbar sind.  
  
 [Sichern von Diensten](securing-services.md)  
 Mithilfe von WCF und vorhandenen Sicherheitsmechanismen können Sie Vertraulichkeit, Integrität, Authentifizierung und Autorisierung in beliebige Dienste implementieren. Sie können auch eine Überprüfung auf Sicherheitserfolge und -misserfolge durchführen.  
  
 [Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten](./creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 Die Anforderungen zum Verwenden eines Dienstes, der über die Interoperabilität mit Diensten und Clients auf beliebigen anderen Plattformen oder Betriebssystemen verfügt, sind in der WS-I Basic Profile 1.1-Spezifikation beschrieben.  
  
## <a name="reference"></a>Referenz  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Grundlegender Programmierlebenszyklus](basic-programming-lifecycle.md)  
  
 [Entwerfen und Implementieren von Diensten](designing-and-implementing-services.md)  
  
 [Hosting-Dienste](hosting-services.md)  
  
 [Erstellen von Clients](building-clients.md)  
  
 [Einführung in die Erweiterbarkeit](introduction-to-extensibility.md)  
  
 [Verwaltung und Diagnose](./diagnostics/index.md)  
  
## <a name="see-also"></a>Siehe auch

- [Einfache WCF-Programmierung](basic-wcf-programming.md)
- [Konzeptionelle Übersicht](conceptual-overview.md)
- [Details zur WCF-Funktion](./feature-details/index.md)
