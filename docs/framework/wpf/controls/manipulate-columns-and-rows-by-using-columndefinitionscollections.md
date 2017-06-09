---
title: "Gewusst wie: Bearbeiten von Spalten und Zeilen mithilfe von ColumnDefinitionsCollections und RowDefinitionsCollections | Microsoft Docs"
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
  - "Klassen, ColumnDefinitionCollection"
  - "Klassen, RowDefinitionCollection"
  - "ColumnDefinitionCollection-Klasse"
  - "Steuerelemente, Grid-Klasse"
  - "Grid-Steuerelement, ColumnDefinitionCollection-Klasse"
  - "Grid-Steuerelement, RowDefinitionCollection-Klasse"
  - "RowDefinitionCollection-Klasse"
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Bearbeiten von Spalten und Zeilen mithilfe von ColumnDefinitionsCollections und RowDefinitionsCollections
Dieses Beispiel veranschaulicht die Verwendung der Methoden der <xref:System.Windows.Controls.ColumnDefinitionCollection>\-Klasse und der <xref:System.Windows.Controls.RowDefinitionCollection>\-Klasse, um beispielsweise Zeilen\- oder Spalteninhalt hinzuzufügen, zu löschen oder zu zählen.  Sie können zum Beispiel <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A> oder <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> auf die Elemente anwenden, die in <xref:System.Windows.Controls.ColumnDefinition> oder <xref:System.Windows.Controls.RowDefinition> enthalten sind.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.Grid>\-Element mit dem <xref:System.Windows.FrameworkElement.Name%2A> `grid1` erstellt.  Der <xref:System.Windows.Controls.Grid> enthält einen <xref:System.Windows.Controls.StackPanel>, der <xref:System.Windows.Controls.Button>\-Elemente enthält, wovon jedes durch eine andere Auflistungsmethode kontrolliert wird.  Wenn Sie auf einen <xref:System.Windows.Controls.Button> klicken, wird in der Code\-Behind\-Datei ein Methodenaufruf aktiviert.  
  
 [!code-xml[ColumnDefinitionsGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird eine Reihe von benutzerdefinierten Methoden definiert. Jede dieser Methoden entspricht einem <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis in der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Datei.  Die Spalten\- und Zeilenanzahl im <xref:System.Windows.Controls.Grid> können Sie mit zahlreichen Möglichkeiten ändern, unter anderem durch Hinzufügen oder Entfernen von Zeilen und Spalten und Zählen der Gesamtanzahl von Zeilen und Spalten.  Sie können zur Vermeidung der Ausnahmen <xref:System.ArgumentOutOfRangeException> und <xref:System.ArgumentException> die Fehlerüberprüfungsverfahren der <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A>\-Methode verwenden.  
  
 [!code-csharp[ColumnDefinitionsGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.Controls.ColumnDefinitionCollection>   
 <xref:System.Windows.Controls.RowDefinitionCollection>