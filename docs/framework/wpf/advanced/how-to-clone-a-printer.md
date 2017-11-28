---
title: 'Gewusst wie: Klonen eines Druckers'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 303cb9c1c5b6521839987a56cdc008eac0559cf1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="b6c5c-102">Gewusst wie: Klonen eines Druckers</span><span class="sxs-lookup"><span data-stu-id="b6c5c-102">How to: Clone a Printer</span></span>
<span data-ttu-id="b6c5c-103">Die meisten Unternehmen werden, zu einem späteren Zeitpunkt mehrere Drucker desselben Modells kaufen.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="b6c5c-104">In der Regel sind diese alle mit nahezu identischen Konfigurationseinstellungen installiert.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="b6c5c-105">Installieren alle Drucker kann zeitaufwändig sein und fehleranfällig.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="b6c5c-106">Die <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> Namespace und die <xref:System.Printing.PrintServer.InstallPrintQueue%2A> -Klasse, die mit verfügbar gemacht werden [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] ermöglicht es sofort aus einer vorhandenen Druckwarteschlange installieren eine beliebige Anzahl von zusätzlichen Druckwarteschlangen, die geklont werden.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6c5c-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b6c5c-107">Example</span></span>  
 <span data-ttu-id="b6c5c-108">Im folgenden Beispiel wird eine zweite Druckerwarteschlange von einer vorhandenen Druckwarteschlange geklont.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="b6c5c-109">Die zweite unterscheidet sich von der ersten nur in dessen Namen, Speicherort, Port und freigegebenen Status.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="b6c5c-110">Die wichtigsten Schritte für diese Vorgehensweise sind wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-110">The major steps for doing this are as follows.</span></span>  
  
1.  <span data-ttu-id="b6c5c-111">Erstellen einer <xref:System.Printing.PrintQueue> Objekt für den vorhandenen Drucker, die geklont werden soll.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2.  <span data-ttu-id="b6c5c-112">Erstellen einer <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> aus der <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> von der <xref:System.Printing.PrintQueue>.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="b6c5c-113">Die <xref:System.Collections.DictionaryEntry.Value%2A> für jeden Eintrag in dieses Wörterbuch aufweist und ein Objekt ist eines von abgeleiteten Typen <xref:System.Printing.IndexedProperties.PrintProperty>.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="b6c5c-114">Es gibt zwei Möglichkeiten, den Wert eines Eintrags in diesem Wörterbuch festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    -   <span data-ttu-id="b6c5c-115">Das Wörterbuch zu verwenden **entfernen** und <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> Methoden zu entfernen Sie den Eintrag, und klicken Sie dann erneut mit dem gewünschten Wert hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    -   <span data-ttu-id="b6c5c-116">Das Wörterbuch zu verwenden <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="b6c5c-117">Das folgende Beispiel veranschaulicht beide Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-117">The example below illustrates both ways.</span></span>  
  
3.  <span data-ttu-id="b6c5c-118">Erstellen einer <xref:System.Printing.IndexedProperties.PrintBooleanProperty> Objekt, und seine <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> auf "IsShared" und die zugehörige <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> auf `true`.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4.  <span data-ttu-id="b6c5c-119">Verwenden der <xref:System.Printing.IndexedProperties.PrintBooleanProperty> Objekt, das der Wert der <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>der Eintrag "IsShared".</span><span class="sxs-lookup"><span data-stu-id="b6c5c-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5.  <span data-ttu-id="b6c5c-120">Erstellen einer <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, und seine <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> auf "ShareName" und die zugehörige <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> in eine entsprechende <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6.  <span data-ttu-id="b6c5c-121">Verwenden der <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, das der Wert der <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>der Eintrag "ShareName".</span><span class="sxs-lookup"><span data-stu-id="b6c5c-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7.  <span data-ttu-id="b6c5c-122">Erstellen Sie ein weiteres <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, und seine <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> zu "Location" und die zugehörige <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> in eine entsprechende <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8.  <span data-ttu-id="b6c5c-123">Verwenden Sie das zweite <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, das der Wert der <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>des "Location" Posten.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="b6c5c-124">Erstellt ein Array von <xref:System.String>s.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="b6c5c-125">Jedes Element ist der Name eines Ports auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="b6c5c-126">Verwendung <xref:System.Printing.PrintServer.InstallPrintQueue%2A> So installieren Sie den neuen Drucker mit den neuen Werten.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="b6c5c-127">Ein Beispiel ist unten.</span><span class="sxs-lookup"><span data-stu-id="b6c5c-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="b6c5c-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6c5c-128">See Also</span></span>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [<span data-ttu-id="b6c5c-129">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="b6c5c-129">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="b6c5c-130">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="b6c5c-130">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
