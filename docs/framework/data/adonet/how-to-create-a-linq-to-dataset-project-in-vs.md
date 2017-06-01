---
title: "Vorgehensweise: Erstellen eines LINQ to DataSet-Projekts in Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Erstellen eines LINQ to DataSet-Projekts in Visual Studio
Die unterschiedlichen Arten von [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]\-Projekten benötigen bestimmte importierte Namespaces \(Visual Basic\) oder `using`\-Direktiven \(C\#\) und \-Verweise.  Die Mindestanforderung ist ein Verweis auf \<legacyBold\>System.Core.dll\<\/legacyBold\> und eine `using`\-Direktive für <xref:System.Linq>.  Standardmäßig werden diese angegeben, wenn Sie ein neues [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)]\-Projekt erstellen.  [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] erfordert außerdem einen Verweis auf "System.Data.dll" und "System.Data.DataSetExtensions.dll" sowie eine `Imports`\-Direktive \(Visual Basic\) oder eine `using`\-Direktive \(C\#\).  
  
 Wenn Sie ein Projekt aus einer früheren Version von Visual Studio aktualisieren möchten, müssen Sie diese LINQ\-Verweise möglicherweise manuell bereitstellen.  Darüber hinaus muss u. U. auch das Projekt so eingerichtet werden, dass es sich auf .NET Framework 3.5 bezieht.  
  
> [!NOTE]
>  Wenn Sie über die Eingabeaufforderung erstellen, müssen Sie manuell auf die LINQ\-bezogenen DLLs in `drive`**:**\\Programme\\Reference Assemblies\\Microsoft\\Framework\\v3.5 verweisen.  
  
### So legen Sie .NET Framework 3.5 als Ziel fest  
  
1.  Erstellen Sie in [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] ein neues Visual Basic\- oder C\#\-Projekt. Sie können auch ein in Visual Studio 2005 erstelltes Visual Basic\- oder C\#\-Projekt öffnen und es mit den angezeigten Schritten in ein [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]\-Projekt umwandeln.  
  
2.  Klicken Sie bei einem C\#\-Projekt auf das Menü **Projekt** und dann auf **Eigenschaften**.  
  
    1.  Wählen Sie auf der Eigenschaftenseite **Anwendung** aus der Dropdownliste **Zielframework** \<legacyBold\>.NET Framework 3.5\<\/legacyBold\> aus.  
  
3.  Klicken Sie bei einem Visual Basic\-Projekt auf das Menü **Projekt** und dann auf **Eigenschaften**.  
  
    1.  Klicken Sie auf der Eigenschaftenseite **Kompilieren** auf **Erweiterte Kompilierungsoptionen**, und wählen Sie dann aus der Dropdownliste **Zielframework \(alle Konfigurationen\)** \<legacyBold\>.NET Framework 3.5\<\/legacyBold\> aus.  
  
4.  Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen**, klicken Sie auf die Registerkarte **.NET**, verschieben Sie den Fensterinhalt zum Eintrag **System.Core**, klicken Sie auf ihn, und klicken Sie dann auf **OK**.  
  
5.  Fügen Sie Ihrer Quellcodedatei oder Ihrem Projekt eine `using`\-Direktive oder einen importierten Namespace für <xref:System.Linq> hinzu.  
  
     Weitere Informationen finden Sie unter [using\-Direktive](../Topic/using%20Directive%20\(C%23%20Reference\).md) oder [Gewusst wie: Hinzufügen oder Entfernen von importierten Namespaces \(Visual Basic\)](../Topic/How%20to:%20Add%20or%20Remove%20Imported%20Namespaces%20\(Visual%20Basic\).md).  
  
### So aktivieren Sie die LINQ to DataSet\-Funktionalität  
  
1.  Führen Sie bei Bedarf die oben genannten Schritte aus, um einen Verweis auf \<legacyBold\>System.Core.dll\<\/legacyBold\> und eine `using`\-Direktive oder einen importierten Namespace für \<legacyBold\>System.Linq\<\/legacyBold\> hinzuzufügen.  
  
2.  Klicken Sie in C\# oder Visual Basic auf das Menü **Projekt** und dann auf **Verweis hinzufügen**.  
  
3.  Klicken Sie im Dialogfeld **Verweis hinzufügen** auf die Registerkarte **.NET**, falls diese nicht bereits angezeigt wird.  Verschieben Sie den Fensterinhalt zu den Einträgen **System.Data** und **System.Data.DataSetExtensions**, und klicken Sie auf sie.  Klicken Sie auf **OK**.  
  
4.  Fügen Sie Ihrer Quellcodedatei oder Ihrem Projekt eine `using`\-Direktive oder einen importierten Namespace für <xref:System.Data> hinzu.  Weitere Informationen finden Sie unter [using\-Direktive](../Topic/using%20Directive%20\(C%23%20Reference\).md) oder [Gewusst wie: Hinzufügen oder Entfernen von importierten Namespaces \(Visual Basic\)](../Topic/How%20to:%20Add%20or%20Remove%20Imported%20Namespaces%20\(Visual%20Basic\).md).  
  
5.  Fügen Sie für die LINQ to DataSet\-Funktionalität einen Verweis auf \<legacyBold\>System.Data.DataSetExtensions.dll\<\/legacyBold\> hinzu.  Falls noch nicht vorhanden, fügen Sie einen Verweis auf \<legacyBold\>System.Data.dll\<\/legacyBold\> hinzu.  
  
6.  Fügen Sie bei Bedarf eine `using`\-Direktive oder einen importierten Namespace für `System.Data.Common` bzw. `System.Data.SqlClient` \(je nachdem, wie die Verbindung mit der Datenbank hergestellt wird\) hinzu.  
  
## Siehe auch  
 [Erste Schritte](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)   
 [Getting Started with LINQ](http://msdn.microsoft.com/de-de/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)