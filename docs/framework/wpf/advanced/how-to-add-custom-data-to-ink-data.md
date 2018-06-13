---
title: 'Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu Freihanddaten'
ms.date: 03/30/2017
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
ms.openlocfilehash: 40d883f3d3e1d504c8757c31325aa72a03da37e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544510"
---
# <a name="how-to-add-custom-data-to-ink-data"></a><span data-ttu-id="450b9-102">Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu Freihanddaten</span><span class="sxs-lookup"><span data-stu-id="450b9-102">How to: Add Custom Data to Ink Data</span></span>
<span data-ttu-id="450b9-103">Sie können benutzerdefinierte Daten Freihandeingaben hinzufügen, die zusammen die Freihandeingabe als serialisiert Freihand-Format (ISF) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="450b9-103">You can add custom data to ink that will be saved when the ink is saved as ink serialized format (ISF).</span></span>  <span data-ttu-id="450b9-104">Sie können die benutzerdefinierten Daten zu speichern die <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection>, oder die <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="450b9-104">You can save the custom data to the <xref:System.Windows.Ink.DrawingAttributes>, the <xref:System.Windows.Ink.StrokeCollection>, or the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="450b9-105">Die Möglichkeit zum Speichern von benutzerdefinierter Daten für drei Objekte bietet Ihnen die Möglichkeit, um zu entscheiden, die beste Möglichkeit zum Speichern der Daten.</span><span class="sxs-lookup"><span data-stu-id="450b9-105">Being able to save custom data on three objects gives you the ability to decide the best place to save the data.</span></span>  <span data-ttu-id="450b9-106">Alle drei Klassen verwenden ähnliche Methoden zum Speichern und Zugreifen auf benutzerdefinierte Daten an.</span><span class="sxs-lookup"><span data-stu-id="450b9-106">All three classes use similar methods to store and access custom data.</span></span>  
  
 <span data-ttu-id="450b9-107">Nur die folgenden Typen können als benutzerdefinierte Daten gespeichert werden:</span><span class="sxs-lookup"><span data-stu-id="450b9-107">Only the following types can be saved as custom data:</span></span>  
  
-   <xref:System.Boolean>  
  
-   <span data-ttu-id="450b9-108"><xref:System.Boolean>[]</span><span class="sxs-lookup"><span data-stu-id="450b9-108"><xref:System.Boolean>[]</span></span>  
  
-   <xref:System.Byte>  
  
-   <span data-ttu-id="450b9-109"><xref:System.Byte>[]</span><span class="sxs-lookup"><span data-stu-id="450b9-109"><xref:System.Byte>[]</span></span>  
  
-   <xref:System.Char>  
  
-   <span data-ttu-id="450b9-110"><xref:System.Char>[]</span><span class="sxs-lookup"><span data-stu-id="450b9-110"><xref:System.Char>[]</span></span>  
  
-   <xref:System.DateTime>  
  
-   <span data-ttu-id="450b9-111"><xref:System.DateTime>[]</span><span class="sxs-lookup"><span data-stu-id="450b9-111"><xref:System.DateTime>[]</span></span>  
  
-   <xref:System.Decimal>  
  
-   <span data-ttu-id="450b9-112"><xref:System.Decimal>[]</span><span class="sxs-lookup"><span data-stu-id="450b9-112"><xref:System.Decimal>[]</span></span>  
  
-   <xref:System.Double>  
  
-   <span data-ttu-id="450b9-113"><xref:System.Double>[]</span><span class="sxs-lookup"><span data-stu-id="450b9-113"><xref:System.Double>[]</span></span>  
  
-   <xref:System.Int16>  
  
-   <span data-ttu-id="450b9-114"><xref:System.Int16>[]</span><span class="sxs-lookup"><span data-stu-id="450b9-114"><xref:System.Int16>[]</span></span>  
  
-   <xref:System.Int32>  
  
-   <span data-ttu-id="450b9-115"><xref:System.Int32>[]</span><span class="sxs-lookup"><span data-stu-id="450b9-115"><xref:System.Int32>[]</span></span>  
  
-   <xref:System.Int64>  
  
-   <span data-ttu-id="450b9-116"><xref:System.Int64>[]</span><span class="sxs-lookup"><span data-stu-id="450b9-116"><xref:System.Int64>[]</span></span>  
  
-   <xref:System.Single>  
  
-   <span data-ttu-id="450b9-117"><xref:System.Single>[]</span><span class="sxs-lookup"><span data-stu-id="450b9-117"><xref:System.Single>[]</span></span>  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <span data-ttu-id="450b9-118"><xref:System.UInt16>[]</span><span class="sxs-lookup"><span data-stu-id="450b9-118"><xref:System.UInt16>[]</span></span>  
  
-   <xref:System.UInt32>  
  
-   <span data-ttu-id="450b9-119"><xref:System.UInt32>[]</span><span class="sxs-lookup"><span data-stu-id="450b9-119"><xref:System.UInt32>[]</span></span>  
  
-   <xref:System.UInt64>  
  
-   <span data-ttu-id="450b9-120"><xref:System.UInt64>[]</span><span class="sxs-lookup"><span data-stu-id="450b9-120"><xref:System.UInt64>[]</span></span>  
  
## <a name="example"></a><span data-ttu-id="450b9-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="450b9-121">Example</span></span>  
 <span data-ttu-id="450b9-122">Das folgende Beispiel veranschaulicht das Hinzufügen und Abrufen von benutzerdefinierten Daten aus einer <xref:System.Windows.Ink.StrokeCollection>.</span><span class="sxs-lookup"><span data-stu-id="450b9-122">The following example demonstrates how to add and retrieve custom data from a <xref:System.Windows.Ink.StrokeCollection>.</span></span>  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 <span data-ttu-id="450b9-123">Das folgende Beispiel erstellt eine Anwendung, die zeigt eine <xref:System.Windows.Controls.InkCanvas> und zwei Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="450b9-123">The following example creates an application that displays an <xref:System.Windows.Controls.InkCanvas> and two buttons.</span></span>  <span data-ttu-id="450b9-124">Die Schaltfläche `switchAuthor`, zwei Stifte, die von zwei verschiedenen Autoren verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="450b9-124">The button, `switchAuthor`, enables two pens to be used by two different authors.</span></span>  <span data-ttu-id="450b9-125">Die Schaltfläche mit den `changePenColors` ändert sich die Farbe jedes Strich auf die <xref:System.Windows.Controls.InkCanvas> gemäß den Autor.</span><span class="sxs-lookup"><span data-stu-id="450b9-125">The button `changePenColors` changes the color of each stroke on the <xref:System.Windows.Controls.InkCanvas> according to the author.</span></span>  <span data-ttu-id="450b9-126">Die Anwendung definiert zwei <xref:System.Windows.Ink.DrawingAttributes> -Objekte und fügt eine benutzerdefinierte Eigenschaft für jede Anwendung, der angibt, welche Autor gezeichnet wurde die <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="450b9-126">The application defines two <xref:System.Windows.Ink.DrawingAttributes> objects and adds a custom property to each one that indicates which author drew the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="450b9-127">Wenn der Benutzer klickt `changePenColors`, die Anwendung ändert die Darstellung des Strichs entsprechend dem Wert der benutzerdefinierten Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="450b9-127">When the user clicks `changePenColors`, the application changes the appearance of the stroke according to the value of the custom property.</span></span>  
  
 [!code-xaml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
