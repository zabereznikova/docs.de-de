---
title: Erweitern von ServiceHost und der Dienstmodellebene
ms.date: 03/30/2017
helpviewer_keywords:
- extending service models [WCF]
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
ms.openlocfilehash: 184719f5c3e2e3830d7e1c9c69b73649b66fff34
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273034"
---
# <a name="extending-servicehost-and-the-service-model-layer"></a>Erweitern von ServiceHost und der Dienstmodellebene

Die Dienstmodellebene ist dafür verantwortlich, eingehende Nachrichten aus den zugrunde liegenden Kanälen abzufangen, sie in Methodenaufrufe per Anwendungscode zu übersetzen und die Ergebnisse zurück an den Aufrufer zu senden. Dienstmodellerweiterungen ändern bzw. implementieren Ausführungs- oder Kommunikationsverhalten und Funktionen wie Verteileroptionen, benutzerdefiniertes Verhalten, Nachrichten- oder Parameterinterceptoren und andere Erweiterbarkeitsfunktionen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Erweitern von Clients](extending-clients.md)  
 Beschreibt die Schnittstellen, die die Client-Runtime abfangen und bearbeiten können, sowie die Klassen, in die Sie Ihre benutzerdefinierten Erweiterungen in Clientanwendungen einfügen können. Sie können beispielsweise eine benutzerdefinierte Clientnachrichtenprotokollierung, benutzerdefinierte Nachrichtenserialisierung usw. durchführen.  
  
 [Erweitern von Verteilern](extending-dispatchers.md)  
 Beschreibt die Schnittstellen, die die Dienst-Runtime abfangen und bearbeiten können, sowie die Klassen, in die Sie Ihre benutzerdefinierten Erweiterungen in Dienstanwendungen einfügen können. Sie können beispielsweise eine benutzerdefinierte Dienstprotokollierung, eine Nachrichtenvalidierung aufseiten des Dienstes, einen benutzerdefinierten Versand usw. durchführen.  
  
 [Erweiterbare Objekte](extensible-objects.md)  
 Beschreibt die fünf erweiterbaren Objekte und das <xref:System.ServiceModel.IExtensibleObject%601>-Muster. Das erweiterbare Objektmuster wird verwendet, um entweder vorhandene Laufzeitklassen um neue Funktionen zu erweitern oder um einem Objekt neue Zustandsfunktionen hinzuzufügen. Erweiterungen, die einem der erweiterbaren Objekte zugeordnet sind, ermöglichen es Verhalten in verschiedenen Phasen der Verarbeitung, auf gemeinsam verwendete Zustände und Funktionen zuzugreifen, die an ein zugängliches und allgemeines erweiterbares Objekt angefügt sind.  
  
 [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md)  
 Zum Ändern von Einstellungen für oder zum Einfügen von Erweiterungen in der WCF-Laufzeit verwenden Sie Verhalten. WCF umfasst vom System implementierte Verhalten zum Steuern von Einschränkungen, Instanzen und anderen Dienst- und Vorgangsaspekten. Dieser Abschnitt beschreibt, wie Sie Ihre eigenen benutzerdefinierten Verhalten erstellen und sie programmatisch bzw. mit Konfigurationsdateien verfügbar machen können.  
  
 [Erweitern des Hosting mit ServiceHostFactory](extending-hosting-using-servicehostfactory.md)  
 Beschreibt, wie Sie <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> erweitern und die <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType>-Klassen verwenden können, um die Hostumgebung anzupassen.  
  
## <a name="reference"></a>Referenz  
  
## <a name="related-sections"></a>Verwandte Abschnitte
