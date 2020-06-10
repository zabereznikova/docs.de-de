---
title: WCF-Suche
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 63c6589cb2ecff9f0a5e7c8bb61b454f6516c98c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600178"
---
# <a name="wcf-discovery"></a>WCF-Suche
Windows Communication Foundation (WCF) bietet Unterstützung, damit Dienste zur Laufzeit auf interoperable Weise erkennbar sind, indem das WS-Discovery-Protokoll verwendet wird. WCF-Dienste können Ihre Verfügbarkeit im Netzwerk mit einer Multicast Nachricht oder einem suchproxyserver ankündigen. Clientanwendungen können ein Netzwerk oder einen Suchproxyserver durchsuchen, um Dienste zu ermitteln, die eine bestimmte Gruppe von Kriterien erfüllen. Die Themen in diesem Abschnitt enthalten eine Übersicht, und das Programmiermodell für diese Funktion wird ausführlich beschrieben.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über die WCF-Suche](wcf-discovery-overview.md)  
 Bietet einen Überblick über die von WCF bereitgestellte WS-Discovery-Unterstützung.  
  
 [Objektmodell der WCF-Suche](wcf-discovery-object-model.md)  
 Beschreibt die Klassen im Objektmodell und die Erweiterbarkeit der WS-Discovery-Unterstützung.  
  
 [Vorgehensweise: Programmgesteuertes Hinzufügen der Ermittelbarkeit zu einem WCF-Dienst und -Client](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 Zeigt, wie Sie einen Windows Communication Foundation (WCF)-Dienst auffindbar machen.  
  
 [Implementieren eines Suchproxys](implementing-a-discovery-proxy.md)  
 Beschreibt die Schritte, die erforderlich sind, um Folgendes zu implementieren: einen Suchproxy, einen erkennbaren Dienst, der sich beim Suchproxy registriert, und einen Client, der den Suchproxy zum Suchen nach dem erkennbaren Dienst verwendet.  
  
 [Versionskontrolle für die Suche](discovery-versioning.md)  
 Bietet eine kurze Übersicht über eine Prototypimplementierung einiger neuer Suchfunktionen. Es enthält außerdem eine Übersicht über die Auswahl der zu verwendenden Suchversion.  
  
 [Konfigurieren der Suche in einer Konfigurationsdatei](configuring-discovery-in-a-configuration-file.md)  
 Beschreibt, wie Sie die Suche in der Konfiguration konfigurieren.  
  
 [Verwenden des Suchclientchannels](using-the-discovery-client-channel.md)  
 Zeigt, wie ein Discovery-Clientchannel beim Schreiben einer WCF-Client Anwendung verwendet wird.
