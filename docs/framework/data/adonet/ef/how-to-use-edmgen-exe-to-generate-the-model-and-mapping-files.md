---
title: "Vorgehensweise: Generieren von Modell- und Zuordnungsdateien mithilfe von EdmGen.exe | Microsoft Docs"
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
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Vorgehensweise: Generieren von Modell- und Zuordnungsdateien mithilfe von EdmGen.exe
In diesem Thema wird veranschaulicht, wie das Tool EDM\-Generator \(EdmGen.exe\) verwendet wird, um die folgenden Dateien auf der Grundlage der Datenbank "School" zu generieren:  
  
-   Ein konzeptionelles Modell \(eine CSDL\-Datei\).  
  
-   Ein Speichermodell \(eine SSDL\-Datei\).  
  
-   Die Zuordnung zwischen dem konzeptionellen Modell und dem Speichermodell \(eine MSL\-Datei\).  
  
-   Code auf Objektebene für Visual Basic oder C\#.  
  
-   Ansichtsdateien.  
  
 Wenn das Tool EdmGen.exe mit dem Befehl \/mode:FullGeneration aufgerufen wird, werden die oben aufgeführten Dateien generiert.  Weitere Informationen zu den Befehlen in EdmGen.exe finden Sie unter [EDM\-Generator \(EdmGen.exe\)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).  
  
 Auch wenn Sie die Modell\- und Zuordnungsdateien mit EdmGen.exe erstellen, müssen Sie das [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]\-Projekt für die Verwendung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] konfigurieren.  Weitere Informationen finden Sie unter [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/de-de/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  Ein mithilfe von EdmGen.exe erstelltes konzeptionelles Modell enthält alle Objekte der Datenbank.  Sie können mithilfe des Entity Data Model\-Assistenten ein konzeptionelles Modell erstellen, das nur bestimmte Objekte enthält.  Weitere Informationen finden Sie unter [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/de-de/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
### So erstellen Sie mithilfe von 'EdmGen.exe' das Modell 'School' für ein Visual Basic\-Projekt  
  
1.  Erstellen der Datenbank "School".  Weitere Informationen finden Sie unter [Creating the School Sample Database](http://msdn.microsoft.com/de-de/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
  
    ```  
  
### So erstellen Sie mithilfe von 'EdmGen.exe' das Modell 'School' für ein C\#\-Projekt  
  
1.  Erstellen der Datenbank "School".  Weitere Informationen finden Sie unter [Creating the School Sample Database](http://msdn.microsoft.com/de-de/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## Siehe auch  
 [Modellieren und Zuordnen](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)   
 [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/de-de/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)   
 [How to: Pre\-Generate Views to Improve Query Performance](http://msdn.microsoft.com/de-de/b18a9d16-e10b-4043-ba91-b632f85a2579)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/de-de/91076853-0881-421b-837a-f582f36be527)   
 [Gewusst wie: Überprüfen von Modell\- und Zuordnungsdateien mithilfe von EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)