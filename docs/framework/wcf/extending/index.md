---
title: Erweitern von WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
ms.openlocfilehash: 24ad74f04a3ac31d0b0d0d87f0d74f88c0521f50
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768718"
---
# <a name="extending-wcf"></a>Erweitern von WCF
Windows Communication Foundation (WCF) können Sie ändern und erweitern die Laufzeitkomponenten präzise steuern, und erweitern, dienstbasierte Anwendungen. Die Themen in diesem Abschnitt enthalten eingehende Informationen zur Erweiterbarkeitsarchitektur. Weitere Informationen zur grundlegenden Programmierung finden Sie unter [Basis-WCF-Programmierung](../../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erweitern von ServiceHost und der Dienstmodellebene](../../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)  
 Die Dienstmodellebene ist dafür verantwortlich, eingehende Nachrichten aus den zugrunde liegenden Kanälen abzufangen, sie in Methodenaufrufe per Anwendungscode zu übersetzen und die Ergebnisse zurück an den Aufrufer zu senden.  Dienstmodellerweiterungen ändern bzw. implementieren Ausführungs- oder Kommunikationsverhalten und Funktionen wie Verteileroptionen, Nachrichten- oder Parameterinterceptoren und andere Erweiterbarkeitsfunktionen.  
  
 [Erweitern von Bindungen](../../../../docs/framework/wcf/extending/extending-bindings.md)  
 Bindungen sind Objekte, die die zum Herstellen einer Verbindung zu einem Endpunkt erforderlichen Kommunikationsdetails beschreiben. Bindungserweiterungen oder benutzerdefinierte Bindungen implementieren die benutzerdefinierte Kommunikationsfunktionalität, die erforderlich ist, um Anwendungsfunktionen zu unterstützen.  
  
 [Erweitern der Kanalschicht](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
 Die Kanalebene liegt unterhalb der Dienstmodellebene und ist für den Austausch von Nachrichten zwischen Clients und Diensten verantwortlich. Kanalerweiterungen können neue Protokollfunktionalität implementieren, zum Beispiel Sicherheit. Kanalerweiterungen transportieren außerdem Funktionalität, zum Beispiel das Implementieren eines neuen Netzwerktransports, um SOAP-Nachrichten zu übermitteln.  
  
 [Erweitern der Sicherheit](../../../../docs/framework/wcf/extending/extending-security.md)  
 Sicherheit in WCF besteht aus der Übertragung Sicherheit (Integrität, Vertraulichkeit und Authentifizierung), Zugriff auf Steuerelement (Autorisierung) und Überwachung. Die Klassen finden Sie in der `IdentityModel` Namespace werden von WCF für die Zugriffssteuerung verwendet. Wenn Sie die Sicherheitsarchitektur verinnerlichen, können Sie benutzerdefinierte Anspruchstypen für benutzerdefinierte Zugriffssteuerungssysteme erstellen.  
  
 [Erweitern des Metadatensystems](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
 Das WCF-Metadaten-System ist eine Gruppe von Klassen und Schnittstellen, die Metadaten, die zum Implementieren von dienstbasierten Anwendungen darstellen. Ändern bzw. erweitern Sie die Klassen, oder implementieren und konfigurieren Sie die Schnittstellen, um benutzerdefinierte Metadaten wie WDSL-Erweiterungen (Web Services Description Language) oder benutzerdefinierte WS-PolicyAttachments-Assertionen zu exportieren oder zu importieren.  
  
 [Erweitern von Encodern und Serialisierungsprogrammen](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
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
 [Einfache WCF-Programmierung](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [Details zur WCF-Funktion](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [Richtlinien und empfohlene Vorgehensweisen](../../../../docs/framework/wcf/guidelines-and-best-practices.md)
