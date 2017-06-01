---
title: "Gewusst wie: Konvertieren von gebundenen Daten | Microsoft Docs"
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
  - "Binden von Daten, Konvertieren von gebundenen Daten"
  - "Konvertieren, Gebundene Daten"
  - "Datenbindung, Konvertieren von gebundenen Daten"
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Konvertieren von gebundenen Daten
In diesem Beispiel wird gezeigt, wie die Konvertierung auf Daten angewendet wird, die in Bindungen verwendet werden.  
  
 Um Daten während einer Bindung zu konvertieren, müssen Sie eine Klasse erstellen, die die <xref:System.Windows.Data.IValueConverter>\-Schnittstelle implementiert, die wiederum die Methoden <xref:System.Windows.Data.IValueConverter.Convert%2A> und <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> einschließt.  
  
## Beispiel  
 Im folgenden Beispiel wird die Implementierung eines Datenkonverters gezeigt, der den übergebenen Datenwert so konvertiert, dass nur Jahr, Monat und Tag angezeigt werden.  Beim Implementieren der <xref:System.Windows.Data.IValueConverter>\-Schnittstelle sollten Sie die Implementierung mit einem <xref:System.Windows.Data.ValueConversionAttribute>\-Attribut ergänzen, um den Entwicklungstools die Datentypen anzuzeigen, die in die Konvertierung einbezogen sind, wie im folgenden Beispiel:  
  
 [!code-csharp[DataBindingLab#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 Sobald Sie einen Konverter erstellt haben, können Sie ihn als Ressource zur [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Datei hinzufügen.  Im folgenden Beispiel wird dem Namespace, in dem *DateConverter* definiert ist, *src* zugeordnet.  
  
 [!code-xml[DataBindingLab#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 Abschließend können Sie den Konverter in der Bindung mit der folgenden Syntax verwenden.  Im folgenden Beispiel wird der Textinhalt für den <xref:System.Windows.Controls.TextBlock> an *StartDate* gebunden; dabei handelt es sich um eine Eigenschaft einer externen Datenquelle.  
  
 [!code-xml[DataBindingLab#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 Die Stilressourcen, auf die im Beispiel oben verwiesen wird, werden in einem Ressourcenabschnitt definiert, der in diesem Thema nicht gezeigt wird.  
  
## Siehe auch  
 [Implementieren der Bindungsvalidierung](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)