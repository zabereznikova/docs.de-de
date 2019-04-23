---
title: 'Vorgehensweise: Bearbeiten von Spalten und Zeilen mithilfe von ColumnDefinitionsCollections und RowDefinitionsCollections'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
ms.openlocfilehash: f316cced076223edba1d39c9cfb21b9a504b9eee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59978275"
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a><span data-ttu-id="ada2c-102">Vorgehensweise: Bearbeiten von Spalten und Zeilen mithilfe von ColumnDefinitionsCollections und RowDefinitionsCollections</span><span class="sxs-lookup"><span data-stu-id="ada2c-102">How to: Manipulate Columns and Rows by Using ColumnDefinitionsCollections and RowDefinitionsCollections</span></span>
<span data-ttu-id="ada2c-103">Dieses Beispiel zeigt, wie Sie die Methoden in der <xref:System.Windows.Controls.ColumnDefinitionCollection> und <xref:System.Windows.Controls.RowDefinitionCollection> Klassen zum Durchführen von Aktionen wie das Hinzufügen, löschen oder den Inhalt der Zeilen oder Spalten zählen.</span><span class="sxs-lookup"><span data-stu-id="ada2c-103">This example shows how to use the methods in the <xref:System.Windows.Controls.ColumnDefinitionCollection> and <xref:System.Windows.Controls.RowDefinitionCollection> classes to perform actions like adding, clearing, or counting the contents of rows or columns.</span></span> <span data-ttu-id="ada2c-104">Sie können z. B. <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, oder <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> die Elemente, die in enthaltenen eine <xref:System.Windows.Controls.ColumnDefinition> oder <xref:System.Windows.Controls.RowDefinition>.</span><span class="sxs-lookup"><span data-stu-id="ada2c-104">For example, you can <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, or <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> the items that are included in a <xref:System.Windows.Controls.ColumnDefinition> or <xref:System.Windows.Controls.RowDefinition>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ada2c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ada2c-105">Example</span></span>  
 <span data-ttu-id="ada2c-106">Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Grid> -Element mit einem <xref:System.Windows.FrameworkElement.Name%2A> von `grid1`.</span><span class="sxs-lookup"><span data-stu-id="ada2c-106">The following example creates a <xref:System.Windows.Controls.Grid> element with a <xref:System.Windows.FrameworkElement.Name%2A> of `grid1`.</span></span> <span data-ttu-id="ada2c-107">Die <xref:System.Windows.Controls.Grid> enthält eine <xref:System.Windows.Controls.StackPanel> enthält <xref:System.Windows.Controls.Button> Elemente, die jeweils durch eine andere Sammlung-Methode gesteuert.</span><span class="sxs-lookup"><span data-stu-id="ada2c-107">The <xref:System.Windows.Controls.Grid> contains a <xref:System.Windows.Controls.StackPanel> that holds <xref:System.Windows.Controls.Button> elements, each controlled by a different collection method.</span></span> <span data-ttu-id="ada2c-108">Beim Klicken auf eine <xref:System.Windows.Controls.Button>, den Aufruf einer Methode in der CodeBehind-Datei aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="ada2c-108">When you click a <xref:System.Windows.Controls.Button>, it activates a method call in the code-behind file.</span></span>  
  
 [!code-xaml[ColumnDefinitionsGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="ada2c-109">In diesem Beispiel definiert eine Reihe von benutzerdefinierten Methoden, die jeweils entsprechenden zu einem <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis in der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei.</span><span class="sxs-lookup"><span data-stu-id="ada2c-109">This example defines a series of custom methods, each corresponding to a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="ada2c-110">Sie können die Anzahl der Spalten und Zeilen im Ändern der <xref:System.Windows.Controls.Grid> auf verschiedene Weise die hinzufügen oder Entfernen von Zeilen und Spalten aus, und die Gesamtzahl der Zeilen und Spalten enthält.</span><span class="sxs-lookup"><span data-stu-id="ada2c-110">You can change the number of columns and rows in the <xref:System.Windows.Controls.Grid> in several ways, which includes adding or removing rows and columns; and counting the total number of rows and columns.</span></span> <span data-ttu-id="ada2c-111">Um zu verhindern, dass <xref:System.ArgumentOutOfRangeException> und <xref:System.ArgumentException> Ausnahmen, können Sie die Überprüfung auf Fehler durch Funktionen, die die <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> Methode bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ada2c-111">To prevent <xref:System.ArgumentOutOfRangeException> and <xref:System.ArgumentException> exceptions, you can use the error-checking functionality that the <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> method provides.</span></span>  
  
 [!code-csharp[ColumnDefinitionsGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ada2c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ada2c-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.ColumnDefinitionCollection>
- <xref:System.Windows.Controls.RowDefinitionCollection>
