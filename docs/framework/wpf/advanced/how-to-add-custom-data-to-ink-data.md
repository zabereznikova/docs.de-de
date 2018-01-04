---
title: "Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu Freihanddaten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ca44d6a2c42219f7aec76f8007010c24c610138
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-custom-data-to-ink-data"></a><span data-ttu-id="4ec34-102">Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu Freihanddaten</span><span class="sxs-lookup"><span data-stu-id="4ec34-102">How to: Add Custom Data to Ink Data</span></span>
<span data-ttu-id="4ec34-103">Sie können benutzerdefinierte Daten Freihandeingaben hinzufügen, die zusammen die Freihandeingabe als serialisiert Freihand-Format (ISF) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4ec34-103">You can add custom data to ink that will be saved when the ink is saved as ink serialized format (ISF).</span></span>  <span data-ttu-id="4ec34-104">Sie können die benutzerdefinierten Daten zu speichern die <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection>, oder die <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="4ec34-104">You can save the custom data to the <xref:System.Windows.Ink.DrawingAttributes>, the <xref:System.Windows.Ink.StrokeCollection>, or the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="4ec34-105">Die Möglichkeit zum Speichern von benutzerdefinierter Daten für drei Objekte bietet Ihnen die Möglichkeit, um zu entscheiden, die beste Möglichkeit zum Speichern der Daten.</span><span class="sxs-lookup"><span data-stu-id="4ec34-105">Being able to save custom data on three objects gives you the ability to decide the best place to save the data.</span></span>  <span data-ttu-id="4ec34-106">Alle drei Klassen verwenden ähnliche Methoden zum Speichern und Zugreifen auf benutzerdefinierte Daten an.</span><span class="sxs-lookup"><span data-stu-id="4ec34-106">All three classes use similar methods to store and access custom data.</span></span>  
  
 <span data-ttu-id="4ec34-107">Nur die folgenden Typen können als benutzerdefinierte Daten gespeichert werden:</span><span class="sxs-lookup"><span data-stu-id="4ec34-107">Only the following types can be saved as custom data:</span></span>  
  
-   <xref:System.Boolean>  
  
-   <span data-ttu-id="4ec34-108"><xref:System.Boolean>[]</span><span class="sxs-lookup"><span data-stu-id="4ec34-108"><xref:System.Boolean>[]</span></span>  
  
-   <xref:System.Byte>  
  
-   <span data-ttu-id="4ec34-109"><xref:System.Byte>[]</span><span class="sxs-lookup"><span data-stu-id="4ec34-109"><xref:System.Byte>[]</span></span>  
  
-   <xref:System.Char>  
  
-   <span data-ttu-id="4ec34-110"><xref:System.Char>[]</span><span class="sxs-lookup"><span data-stu-id="4ec34-110"><xref:System.Char>[]</span></span>  
  
-   <xref:System.DateTime>  
  
-   <span data-ttu-id="4ec34-111"><xref:System.DateTime>[]</span><span class="sxs-lookup"><span data-stu-id="4ec34-111"><xref:System.DateTime>[]</span></span>  
  
-   <xref:System.Decimal>  
  
-   <span data-ttu-id="4ec34-112"><xref:System.Decimal>[]</span><span class="sxs-lookup"><span data-stu-id="4ec34-112"><xref:System.Decimal>[]</span></span>  
  
-   <xref:System.Double>  
  
-   <span data-ttu-id="4ec34-113"><xref:System.Double>[]</span><span class="sxs-lookup"><span data-stu-id="4ec34-113"><xref:System.Double>[]</span></span>  
  
-   <xref:System.Int16>  
  
-   <span data-ttu-id="4ec34-114"><xref:System.Int16>[]</span><span class="sxs-lookup"><span data-stu-id="4ec34-114"><xref:System.Int16>[]</span></span>  
  
-   <xref:System.Int32>  
  
-   <span data-ttu-id="4ec34-115"><xref:System.Int32>[]</span><span class="sxs-lookup"><span data-stu-id="4ec34-115"><xref:System.Int32>[]</span></span>  
  
-   <xref:System.Int64>  
  
-   <span data-ttu-id="4ec34-116"><xref:System.Int64>[]</span><span class="sxs-lookup"><span data-stu-id="4ec34-116"><xref:System.Int64>[]</span></span>  
  
-   <xref:System.Single>  
  
-   <span data-ttu-id="4ec34-117"><xref:System.Single>[]</span><span class="sxs-lookup"><span data-stu-id="4ec34-117"><xref:System.Single>[]</span></span>  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <span data-ttu-id="4ec34-118"><xref:System.UInt16>[]</span><span class="sxs-lookup"><span data-stu-id="4ec34-118"><xref:System.UInt16>[]</span></span>  
  
-   <xref:System.UInt32>  
  
-   <span data-ttu-id="4ec34-119"><xref:System.UInt32>[]</span><span class="sxs-lookup"><span data-stu-id="4ec34-119"><xref:System.UInt32>[]</span></span>  
  
-   <xref:System.UInt64>  
  
-   <span data-ttu-id="4ec34-120"><xref:System.UInt64>[]</span><span class="sxs-lookup"><span data-stu-id="4ec34-120"><xref:System.UInt64>[]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ec34-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ec34-121">Example</span></span>  
 <span data-ttu-id="4ec34-122">Das folgende Beispiel veranschaulicht das Hinzufügen und Abrufen von benutzerdefinierten Daten aus einer <xref:System.Windows.Ink.StrokeCollection>.</span><span class="sxs-lookup"><span data-stu-id="4ec34-122">The following example demonstrates how to add and retrieve custom data from a <xref:System.Windows.Ink.StrokeCollection>.</span></span>  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 <span data-ttu-id="4ec34-123">Das folgende Beispiel erstellt eine Anwendung, die zeigt eine <xref:System.Windows.Controls.InkCanvas> und zwei Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="4ec34-123">The following example creates an application that displays an <xref:System.Windows.Controls.InkCanvas> and two buttons.</span></span>  <span data-ttu-id="4ec34-124">Die Schaltfläche `switchAuthor`, zwei Stifte, die von zwei verschiedenen Autoren verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4ec34-124">The button, `switchAuthor`, enables two pens to be used by two different authors.</span></span>  <span data-ttu-id="4ec34-125">Die Schaltfläche mit den `changePenColors` ändert sich die Farbe jedes Strich auf die <xref:System.Windows.Controls.InkCanvas> gemäß den Autor.</span><span class="sxs-lookup"><span data-stu-id="4ec34-125">The button `changePenColors` changes the color of each stroke on the <xref:System.Windows.Controls.InkCanvas> according to the author.</span></span>  <span data-ttu-id="4ec34-126">Die Anwendung definiert zwei <xref:System.Windows.Ink.DrawingAttributes> -Objekte und fügt eine benutzerdefinierte Eigenschaft für jede Anwendung, der angibt, welche Autor gezeichnet wurde die <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="4ec34-126">The application defines two <xref:System.Windows.Ink.DrawingAttributes> objects and adds a custom property to each one that indicates which author drew the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="4ec34-127">Wenn der Benutzer klickt `changePenColors`, die Anwendung ändert die Darstellung des Strichs entsprechend dem Wert der benutzerdefinierten Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4ec34-127">When the user clicks `changePenColors`, the application changes the appearance of the stroke according to the value of the custom property.</span></span>  
  
 [!code-xaml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
