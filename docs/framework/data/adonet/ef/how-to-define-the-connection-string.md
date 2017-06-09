---
title: "Vorgehensweise: Definieren der Verbindungszeichenfolge | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
  - "jsharp"
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Vorgehensweise: Definieren der Verbindungszeichenfolge
In diesem Thema ist dargestellt, wie die Verbindungszeichenfolge für die Verbindung mit einem konzeptionellen Modell definiert wird.  Dieses Thema beruht auf dem konzeptionellen [AdventureWorks Sales](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832)\-Modell.  Das AdventureWorks Sales\-Modell wird in den aufgabenbezogenen Themen der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]\-Dokumentation verwendet.  Für dieses Thema muss [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] konfiguriert und das "AdventureWorks Sales"\-Modell definiert worden sein.  Weitere Informationen finden Sie unter [How to: Manually Define the Model and Mapping Files](http://msdn.microsoft.com/de-de/d4fd6864-f2a1-48f0-aa32-1e318775a99a).  Die Verfahren in diesem Thema sind auch im Thema [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/de-de/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e) enthalten.  
  
> [!NOTE]
>  Wenn Sie den [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]\-Assistenten in einem [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]\-Projekt verwenden, wird automatisch eine EDMX\-Datei erstellt und das Projekt für die Verwendung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] konfiguriert.  Weitere Informationen finden Sie unter [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/de-de/dadb058a-c5d9-4c5c-8b01-28044112231d)  
  
### So definieren Sie die Verbindungszeichenfolge für Entity Framework  
  
-   Öffnen Sie die Anwendungskonfigurationsdatei des Projekts \(**app.config**\), und fügen Sie folgende Verbindungszeichenfolge hinzu:  
  
  
  
     Wenn Ihr Projekt über keine Anwendungskonfigurationsdatei verfügt, können Sie eine solche hinzufügen, indem Sie im Menü **Projekt** die Option **Neues Element hinzufügen** auswählen. Wählen Sie anschließend die Kategorie **Allgemein** und **Anwendungskonfigurationsdatei** aus, und klicken Sie auf **Hinzufügen**.  
  
## Siehe auch  
 [Quickstart](http://msdn.microsoft.com/de-de/0bc534be-789f-4819-b9f6-76e51d961675)   
 [How to: Create a New .edmx File](http://msdn.microsoft.com/de-de/beb8189e-e51c-4051-839c-9902c224abf2)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/de-de/91076853-0881-421b-837a-f582f36be527)