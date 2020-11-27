---
title: Erweitern von WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
ms.openlocfilehash: b82dd4fb6a5b41a0160df8680fb1ba65d9a5bd33
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254596"
---
# <a name="extending-wcf"></a>Erweitern von WCF

Mit Windows Communication Foundation (WCF) können Sie Laufzeitkomponenten ändern und erweitern, um Dienst basierte Anwendungen exakt zu steuern und zu erweitern. Die Themen in diesem Abschnitt enthalten eingehende Informationen zur Erweiterbarkeitsarchitektur. Weitere Informationen zur grundlegenden Programmierung finden Sie unter [grundlegende WCF-Programmierung](../basic-wcf-programming.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Erweitern von ServiceHost und der Dienstmodellebene](extending-servicehost-and-the-service-model-layer.md)  
 Die Dienstmodellebene ist dafür verantwortlich, eingehende Nachrichten aus den zugrunde liegenden Kanälen abzufangen, sie in Methodenaufrufe per Anwendungscode zu übersetzen und die Ergebnisse zurück an den Aufrufer zu senden.  Dienstmodellerweiterungen ändern bzw. implementieren Ausführungs- oder Kommunikationsverhalten und Funktionen wie Verteileroptionen, Nachrichten- oder Parameterinterceptoren und andere Erweiterbarkeitsfunktionen.  
  
 [Erweitern von Bindungen](extending-bindings.md)  
 Bindungen sind Objekte, die die zum Herstellen einer Verbindung zu einem Endpunkt erforderlichen Kommunikationsdetails beschreiben. Bindungserweiterungen oder benutzerdefinierte Bindungen implementieren die benutzerdefinierte Kommunikationsfunktionalität, die erforderlich ist, um Anwendungsfunktionen zu unterstützen.  
  
 [Erweitern der Kanalschicht](extending-the-channel-layer.md)  
 Die Kanalebene liegt unterhalb der Dienstmodellebene und ist für den Austausch von Nachrichten zwischen Clients und Diensten verantwortlich. Kanalerweiterungen können neue Protokollfunktionalität implementieren, zum Beispiel Sicherheit. Kanalerweiterungen transportieren außerdem Funktionalität, zum Beispiel das Implementieren eines neuen Netzwerktransports, um SOAP-Nachrichten zu übermitteln.  
  
 [Erweitern der Sicherheit](extending-security.md)  
 Die Sicherheit in WCF besteht aus Übertragungssicherheit (Integrität, Vertraulichkeit und Authentifizierung), Zugriffs Steuerung (Autorisierung) und Überwachung. Die im- `IdentityModel` Namespace gefundenen Klassen werden von WCF für die Zugriffs Steuerung verwendet. Wenn Sie die Sicherheitsarchitektur verinnerlichen, können Sie benutzerdefinierte Anspruchstypen für benutzerdefinierte Zugriffssteuerungssysteme erstellen.  
  
 [Erweitern des Metadatensystems](extending-the-metadata-system.md)  
 Das WCF-Metadatensystem ist eine Gruppe von Klassen und Schnittstellen, die Metadaten darstellen, die für die Implementierung von Dienst basierten Anwendungen erforderlich sind. Ändern bzw. erweitern Sie die Klassen, oder implementieren und konfigurieren Sie die Schnittstellen, um benutzerdefinierte Metadaten wie WDSL-Erweiterungen (Web Services Description Language) oder benutzerdefinierte WS-PolicyAttachments-Assertionen zu exportieren oder zu importieren.  
  
 [Erweitern von Encodern und Serialisierungsprogrammen](extending-encoders-and-serializers.md)  
 Encoder und Serialisierungsprogramme übersetzen Daten von einem Formular in ein anderes. In den Themen in diesem Abschnitt wird erläutert, wie Sie die angegebenen Klassen erweitern, um besondere Anforderungen zu erfüllen.  
  
## <a name="reference"></a>Referenz  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Einfache WCF-Programmierung](../basic-wcf-programming.md)  
  
 [Details zur WCF-Funktion](../feature-details/index.md)  
  
 [Richtlinien und empfohlene Vorgehensweisen](../guidelines-and-best-practices.md)
