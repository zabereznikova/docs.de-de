---
title: 'Gewusst wie: Erstellen eines LINQ to DataSet-Projekts in Visual Studio'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6710d3e9bf52ff10ee8dd545161f0858001f2c40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>Gewusst wie: Erstellen eines LINQ to DataSet-Projekts in Visual Studio
Die unterschiedlichen Arten von [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Projekten benötigen bestimmte importierte Namespaces (Visual Basic) oder `using`-Direktiven (C#) und -Verweise. Die Mindestanforderung ist ein Verweis auf <legacyBold>System.Core.dll</legacyBold> und eine `using`-Direktive für <xref:System.Linq>. Standardmäßig werden diese angegeben, wenn Sie ein neues [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)]-Projekt erstellen. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] erfordert außerdem einen Verweis auf "System.Data.dll" und "System.Data.DataSetExtensions.dll" sowie eine `Imports`-Direktive (Visual Basic) oder eine `using`-Direktive (C#).  
  
 Wenn Sie ein Projekt aus einer früheren Version von Visual Studio aktualisieren möchten, müssen Sie diese LINQ-Verweise möglicherweise manuell bereitstellen. Darüber hinaus muss u. U. auch das Projekt so eingerichtet werden, dass es sich auf .NET Framework 3.5 bezieht.  
  
> [!NOTE]
>  Wenn Sie über eine Eingabeaufforderung erstellen, müssen Sie manuell die LINQ-bezogenen DLLs in verweisen `drive` **:**\Programme\Reference Assemblies\Microsoft\Framework\v3.5.  
  
### <a name="to-target-the-net-framework-35"></a>So legen Sie .NET Framework 3.5 als Ziel fest  
  
1.  Erstellen Sie in [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] ein neues Visual Basic- oder C#-Projekt. Sie können auch ein in Visual Studio 2005 erstelltes Visual Basic- oder C#-Projekt öffnen und es mit den auf dem Bildschirm angezeigten Schritten in ein [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Projekt umwandeln.  
  
2.  Ein C#-Projekt, klicken Sie auf die **Projekt** Menü, und klicken Sie dann auf **Eigenschaften**.  
  
    1.  In der **Anwendung** Eigenschaftenseite, wählen Sie .NET Framework 3.5 in der **Zielframework** Dropdown-Liste.  
  
3.  Ein Visual Basic-Projekt, klicken Sie auf die **Projekt** Menü, und klicken Sie dann auf **Eigenschaften**.  
  
    1.  In der **Kompilieren** auf der Seite klicken Sie auf **Erweiterte Kompilierungsoptionen** und wählen Sie dann auf .NET Framework 3.5 in der **Zielframework (alle Konfigurationen)** Dropdown-Liste.  
  
4.  Auf der **Projekt** Menü klicken Sie auf **Verweis hinzufügen**, klicken Sie auf die **.NET** Registerkarte, führen Sie einen Bildlauf nach unten bis zum **"System.Core"**, klicken Sie darauf, und klicken Sie dann auf  **OK**.  
  
5.  Fügen Sie Ihrer Quellcodedatei oder Ihrem Projekt eine `using`-Direktive oder einen importierten Namespace für <xref:System.Linq> hinzu.  
  
     Weitere Informationen finden Sie unter [using-Direktive](~/docs/csharp/language-reference/keywords/using-directive.md) oder [wie: Hinzufügen oder Entfernen von importierten Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).  
  
### <a name="to-enable-linq-to-dataset-functionality"></a>So aktivieren Sie die LINQ to DataSet-Funktionalität  
  
1.  Führen Sie bei Bedarf die oben genannten Schritte aus, um einen Verweis auf <legacyBold>System.Core.dll</legacyBold> und eine `using`-Direktive oder einen importierten Namespace für <legacyBold>System.Linq</legacyBold> hinzuzufügen.  
  
2.  In c# oder Visual Basic, klicken Sie auf die **Projekt** Menü, und klicken Sie dann auf **Verweis hinzufügen**.  
  
3.  In der **Verweis hinzufügen** (Dialogfeld), klicken Sie auf die **.NET** Registerkarte, wenn er nicht bereits angezeigt wird. Führen Sie einen Bildlauf nach unten bis zum **"System.Data"** und **System.Data.DataSetExtensions** , und klicken Sie auf sie. Klicken Sie auf die **OK** Schaltfläche.  
  
4.  Fügen Sie Ihrer Quellcodedatei oder Ihrem Projekt eine `using`-Direktive oder einen importierten Namespace für <xref:System.Data> hinzu. Weitere Informationen finden Sie unter [using-Direktive](~/docs/csharp/language-reference/keywords/using-directive.md) oder [wie: Hinzufügen oder Entfernen von importierten Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).  
  
5.  Fügen Sie für die LINQ to DataSet-Funktionalität einen Verweis auf <legacyBold>System.Data.DataSetExtensions.dll</legacyBold> hinzu. Falls noch nicht vorhanden, fügen Sie einen Verweis auf <legacyBold>System.Data.dll</legacyBold> hinzu.  
  
6.  Fügen Sie bei Bedarf eine `using`-Direktive oder einen importierten Namespace für `System.Data.Common` bzw. `System.Data.SqlClient` (je nachdem, wie die Verbindung mit der Datenbank hergestellt wird) hinzu.  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
 [Erste Schritte mit LINQ](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)
