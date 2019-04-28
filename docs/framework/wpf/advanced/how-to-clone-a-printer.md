---
title: 'Vorgehensweise: Klonen eines Druckers'
ms.date: 03/30/2017
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
ms.openlocfilehash: 09a445da068f0141b9526e0228df8be0105498c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776544"
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="58821-102">Vorgehensweise: Klonen eines Druckers</span><span class="sxs-lookup"><span data-stu-id="58821-102">How to: Clone a Printer</span></span>
<span data-ttu-id="58821-103">Die meisten Unternehmen werden irgendwann mehrere Drucker desselben Modells erwerben.</span><span class="sxs-lookup"><span data-stu-id="58821-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="58821-104">Diese werden alle in der Regel mit nahezu identischen Konfigurationseinstellungen installiert.</span><span class="sxs-lookup"><span data-stu-id="58821-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="58821-105">Installieren die einzelnen Drucker kann sehr zeitaufwändig sein und fehleranfällig.</span><span class="sxs-lookup"><span data-stu-id="58821-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="58821-106">Die <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> Namespace und die <xref:System.Printing.PrintServer.InstallPrintQueue%2A> -Klasse, die mit Microsoft .NET Framework verfügbar gemacht werden ermöglicht, eine beliebige Anzahl von zusätzlichen Druckwarteschlangen, die geklont werden sofort aus einer vorhandenen Druckwarteschlange zu installieren.</span><span class="sxs-lookup"><span data-stu-id="58821-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with Microsoft .NET Framework makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58821-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58821-107">Example</span></span>  
 <span data-ttu-id="58821-108">Im folgenden Beispiel wird eine zweite Druckwarteschlange aus einer vorhandenen Druckwarteschlange geklont.</span><span class="sxs-lookup"><span data-stu-id="58821-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="58821-109">Die zweite, die von der ersten unterscheidet sich nur in dessen Namen, Speicherort, Port und freigegebenen Status.</span><span class="sxs-lookup"><span data-stu-id="58821-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="58821-110">Die wichtigsten Schritte dazu sind wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="58821-110">The major steps for doing this are as follows.</span></span>  
  
1. <span data-ttu-id="58821-111">Erstellen Sie eine <xref:System.Printing.PrintQueue> Objekt für den vorhandenen Drucker, die geklont werden.</span><span class="sxs-lookup"><span data-stu-id="58821-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2. <span data-ttu-id="58821-112">Erstellen Sie eine <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> aus der <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> von der <xref:System.Printing.PrintQueue>.</span><span class="sxs-lookup"><span data-stu-id="58821-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="58821-113">Die <xref:System.Collections.DictionaryEntry.Value%2A> -Eigenschaft für jeden Eintrag in diesem Wörterbuch ist ein Objekt vom Typ abgeleitet <xref:System.Printing.IndexedProperties.PrintProperty>.</span><span class="sxs-lookup"><span data-stu-id="58821-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="58821-114">Es gibt zwei Möglichkeiten, den Wert eines Eintrags in dieses Wörterbuch festlegen.</span><span class="sxs-lookup"><span data-stu-id="58821-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    - <span data-ttu-id="58821-115">Verwenden des Wörterbuchs **entfernen** und <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> Methoden entfernen Sie den Eintrag, und klicken Sie dann erneut mit dem gewünschten Wert hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="58821-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    - <span data-ttu-id="58821-116">Verwenden des Wörterbuchs <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="58821-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="58821-117">Das folgende Beispiel veranschaulicht beide Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="58821-117">The example below illustrates both ways.</span></span>  
  
3. <span data-ttu-id="58821-118">Erstellen einer <xref:System.Printing.IndexedProperties.PrintBooleanProperty> Objekt, und legen dessen <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> auf "IsShared" und die zugehörige <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> zu `true`.</span><span class="sxs-lookup"><span data-stu-id="58821-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4. <span data-ttu-id="58821-119">Verwenden der <xref:System.Printing.IndexedProperties.PrintBooleanProperty> Objekt, das der Wert der <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>des "IsShared"-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="58821-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5. <span data-ttu-id="58821-120">Erstellen einer <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, und legen dessen <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> auf "ShareName" und die zugehörige <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> auf einen entsprechenden <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="58821-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6. <span data-ttu-id="58821-121">Verwenden der <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, das der Wert der <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>des "Freigabename"-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="58821-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7. <span data-ttu-id="58821-122">Erstellen Sie eine weitere <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, und legen dessen <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> , "Location" und die zugehörige <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> auf einen entsprechenden <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="58821-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8. <span data-ttu-id="58821-123">Im zweiten <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, das der Wert der <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>die "Location"-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="58821-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="58821-124">Erstellt ein Array von <xref:System.String>s.</span><span class="sxs-lookup"><span data-stu-id="58821-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="58821-125">Jedes Element ist der Name eines Ports auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="58821-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="58821-126">Verwendung <xref:System.Printing.PrintServer.InstallPrintQueue%2A> So installieren Sie den neuen Drucker mit den neuen Werten.</span><span class="sxs-lookup"><span data-stu-id="58821-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="58821-127">Ein Beispiel ist unten.</span><span class="sxs-lookup"><span data-stu-id="58821-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](~/samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="58821-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58821-128">See also</span></span>

- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="58821-129">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="58821-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="58821-130">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="58821-130">Printing Overview</span></span>](printing-overview.md)
