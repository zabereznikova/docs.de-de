---
title: Konfiguration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86a6e12f-73b5-450e-8725-f4ca5fe0702c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3eee9f955ca75d799b9e5384e47df527934a595f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="configuration"></a>Konfiguration
In diesem Thema werden alle Ausnahmen aufgelistet, die von der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Konfiguration generiert werden.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|ConfigBindingCannotBeConfigured|Die Bindung für den Dienstendpunkt kann nicht konfiguriert werden.|  
|ConfigElementKeyNull|Der spezifische Konfigurationselementschlüssel kann nicht NULL sein.|  
|ConfigExtensionTypeNotRegisteredInCollection|Der spezifische Erweiterungstyp wird nicht in der spezifischen Erweiterungsauflistung registriert.|  
|ConfigIndexOutOfRange|Der Wert für das spezifische Attribut liegt außerhalb des Bereichs.|  
|ConfigInvalidBindingConfigurationName|Die spezifische Konfiguration hat keine Bindung mit dem spezifischen Namen.|  
|ConfigInvalidBindingName|Die spezifische Konfiguration hat keine Bindung mit dem spezifischen Namen. Dies ist ein ungültiger Wert für die Bindung.|  
|ConfigInvalidCommonEndpointBehaviorType|Die spezifische Verhaltenserweiterung kann nicht zum gemeinsamen Endpunktverhalten hinzugefügt werden, da der spezifische Typ nicht von ihr implementiert wird.|  
|ConfigInvalidCommonServiceBehaviorType|Die spezifische Verhaltenserweiterung kann nicht zum gemeinsamen Dienstverhalten hinzugefügt werden, da der spezifische Typ nicht von ihr implementiert wird.|  
|ConfigInvalidEndpointBehaviorType|Die spezifische Verhaltenserweiterung kann nicht zum spezifischen Endpunktverhalten hinzugefügt werden, da die IServiceBehavior-Schnittstelle nicht von dem zugrunde liegenden Verhaltenstyp implementiert wird.|  
|ConfigInvalidExtensionType|Der spezifische Typ muss von der spezifischen Erweiterung abgeleitet sein, die in der Auflistung verwendet werden soll.|  
|ConfigInvalidServiceBehaviorType|Die spezifische Verhaltenserweiterung kann nicht zum Dienstverhalten mit dem spezifischen Namen hinzugefügt werden, da die IServiceBehavior-Schnittstelle nicht von dem zugrunde liegenden Verhaltenstyp implementiert wird.|  
|ConfigMessageEncodingAlreadyInBinding|Das bestimmte Nachrichtencodierungselement kann nicht hinzugefügt werden. Es ist bereits ein weiteres Nachrichtencodierungselement in der spezifischen Bindung vorhanden. Es kann nur ein Nachrichtencodierungselement für jede Bindung geben.|  
|ConfigNoExtensionCollectionAssociatedWithType|Die Erweiterungsauflistung, die der Erweiterung des spezifischen Typs zugeordnet ist, kann nicht gefunden werden.|  
|ConfigSectionNotFound|Der spezifische Konfigurationsabschnitt kann nicht erstellt werden. In der Datei Machine.config fehlen Informationen. Überprüfen Sie, dass dieser Konfigurationsabschnitt ordnungsgemäß registriert wird und dass der Abschnittsname korrekt geschrieben ist. Führen Sie für Windows Communication Foundation-Abschnitte ServiceModelReg.exe -i aus, um diesen Fehler zu beheben.|  
|ConfigTransportAlreadyInBinding|Das spezifische Transportelement kann nicht hinzugefügt werden. Es ist bereits ein weiteres Transportelement in der spezifischen Bindung vorhanden. Es kann nur ein Nachrichtencodierungselement für jede Bindung geben.|
