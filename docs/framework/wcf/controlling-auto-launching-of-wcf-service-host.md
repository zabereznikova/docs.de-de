---
title: "Steuern des automatischen Starts des WCF-Diensthosts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WcfOptions"
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Steuern des automatischen Starts des WCF-Diensthosts
Sie haben die Möglichkeit zum Steuern der Autostartfunktion des [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Diensthosts \(WcfSvcHost.exe\) für ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst\-Bibliotheksprojekt beim Debuggen eines anderen Projekts in der gleichen [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]\-Projektmappe \(bei Projektmappen mit mehreren Projekten\).  
  
 Klicken Sie hierzu im Projektmappen\-Explorermit der rechten Maustaste auf das Projekt für den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst, wählen Sie **Eigenschaften**, und klicken Sie anschließend auf die Registerkarte **WCF\-Optionen**.Das Kontrollkästchen **WCF\-Diensthost beim Debuggen eines anderen Projekts in der gleichen Projektmappe starten** ist standardmäßig aktiviert.Deaktivieren Sie dieses Kontrollkästchen, wenn der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensthost für dieses bestimmte Projekt beim Debuggen eines anderen Projekts in der gleichen Projektmappe nicht gestartet werden soll.  
  
 Dieses Verhalten wirkt sich weder auf das F5\-Debugging noch auf die Funktionen zum Hinzufügen von Dienstverweisen für dieses Projekt aus.  
  
 Diese Option steht für die folgenden Projekte zur Verfügung:  
  
-   Bibliotheksprojekt für [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst  
  
-   Bibliotheksprojekt für sequenziellen Workflowdienst  
  
-   Bibliotheksprojekt für Statuscomputerworkflowdienst  
  
-   Bibliotheksprojekt für Syndication\-Dienst  
  
## Siehe auch  
 [WCF\-Diensthost \(WcfSvcHost.exe\)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)