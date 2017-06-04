---
title: "Gewusst wie: Abrufen von Drucksystemobjekt-Eigenschaften ohne Reflektion | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PrintSystemObject, Abrufen von Eigenschaften"
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Abrufen von Drucksystemobjekt-Eigenschaften ohne Reflektion
Die Aufgliederung der Eigenschaften \(und Typen dieser Eigenschaften\) eines Objekts mithilfe von Reflektion kann die Anwendungsleistung beeinträchtigen.  Der <xref:System.Printing.IndexedProperties>\-Namespace bietet eine Möglichkeit, diese Informationen mithilfe der Reflektion abzurufen.  
  
## Beispiel  
 Dazu müssen die folgenden Schritte ausgeführt werden.  
  
1.  Erstellen Sie eine Instanz des Typs.  Im folgenden Beispiel wird der <xref:System.Printing.PrintQueue>\-Typ aus [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] verwendet. Für Typen, die Sie von <xref:System.Printing.PrintSystemObject> ableiten, können Sie den Code leicht anpassen.  
  
2.  Erstellen Sie ein <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> aus der <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> für diesen Typ.  Die <xref:System.Collections.DictionaryEntry.Value%2A>\-Eigenschaft für jeden Eintrag in diesem Wörterbuch ist ein Objekt, das zu einem der von <xref:System.Printing.IndexedProperties.PrintProperty> abgeleiteten Typen gehört.  
  
3.  Listen Sie die Member des Wörterbuchs auf.  Gehen Sie für jeden Member wie folgt vor.  
  
4.  Wandeln Sie den Wert jedes Eintrags in <xref:System.Printing.IndexedProperties.PrintProperty> um, und erstellen Sie damit ein <xref:System.Printing.IndexedProperties.PrintProperty>\-Objekt.  
  
5.  Rufen Sie den <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A>\-Typ für jedes <xref:System.Printing.IndexedProperties.PrintProperty>\-Objekt ab.  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## Siehe auch  
 <xref:System.Printing.IndexedProperties.PrintProperty>   
 <xref:System.Printing.PrintSystemObject>   
 <xref:System.Printing.IndexedProperties>   
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Collections.DictionaryEntry>   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)