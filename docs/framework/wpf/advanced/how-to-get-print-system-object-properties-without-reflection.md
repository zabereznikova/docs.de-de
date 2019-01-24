---
title: 'Vorgehensweise: Abrufen von Drucksystemobjekt-Eigenschaften ohne Reflektion'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
ms.openlocfilehash: b081586d201bed537c086447c4ddb116f179fbca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693252"
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a><span data-ttu-id="a39aa-102">Vorgehensweise: Abrufen von Drucksystemobjekt-Eigenschaften ohne Reflektion</span><span class="sxs-lookup"><span data-stu-id="a39aa-102">How to: Get Print System Object Properties Without Reflection</span></span>
<span data-ttu-id="a39aa-103">Mithilfe von Reflektion zum aufschlüsseln von Eigenschaften (und die Typen der Eigenschaften) für ein Objekt kann die Leistung der Anwendung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="a39aa-103">Using reflection to itemize the properties (and the types of those properties) on an object can slow application performance.</span></span> <span data-ttu-id="a39aa-104">Die <xref:System.Printing.IndexedProperties> Namespace bietet eine Möglichkeit zum Abrufen dieser Informationen mit der Verwendung von Reflektion.</span><span class="sxs-lookup"><span data-stu-id="a39aa-104">The <xref:System.Printing.IndexedProperties> namespace provides a means to getting this information with using reflection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a39aa-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a39aa-105">Example</span></span>  
 <span data-ttu-id="a39aa-106">Die Schritte dazu sind wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="a39aa-106">The steps for doing this are as follows.</span></span>  
  
1.  <span data-ttu-id="a39aa-107">Erstellen Sie eine Instanz des Typs.</span><span class="sxs-lookup"><span data-stu-id="a39aa-107">Create an instance of the type.</span></span> <span data-ttu-id="a39aa-108">Im folgenden Beispiel wird der Typ ist der <xref:System.Printing.PrintQueue> Typ, der in Microsoft .NET Framework, aber nahezu identischen Code enthalten ist, sollte für Typen, die Sie eine Ableitung aus funktionieren <xref:System.Printing.PrintSystemObject>.</span><span class="sxs-lookup"><span data-stu-id="a39aa-108">In the example below, the type is the <xref:System.Printing.PrintQueue> type that ships with Microsoft .NET Framework, but nearly identical code should work for types that you derive from <xref:System.Printing.PrintSystemObject>.</span></span>  
  
2.  <span data-ttu-id="a39aa-109">Erstellen Sie eine <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> aus des Typs des <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="a39aa-109">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the type's <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span></span> <span data-ttu-id="a39aa-110">Die <xref:System.Collections.DictionaryEntry.Value%2A> -Eigenschaft für jeden Eintrag in diesem Wörterbuch ist ein Objekt vom Typ abgeleitet <xref:System.Printing.IndexedProperties.PrintProperty>.</span><span class="sxs-lookup"><span data-stu-id="a39aa-110">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span>  
  
3.  <span data-ttu-id="a39aa-111">Auflisten der Elemente des Wörterbuchs.</span><span class="sxs-lookup"><span data-stu-id="a39aa-111">Enumerate the members of the dictionary.</span></span> <span data-ttu-id="a39aa-112">Führen Sie die folgenden Schritte aus, für jede von diesen.</span><span class="sxs-lookup"><span data-stu-id="a39aa-112">For each of them, do the following.</span></span>  
  
4.  <span data-ttu-id="a39aa-113">Nach-oben-wandeln Sie den Wert jedes Eintrags in <xref:System.Printing.IndexedProperties.PrintProperty> und verwenden sie zum Erstellen einer <xref:System.Printing.IndexedProperties.PrintProperty> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a39aa-113">Up-cast the value of each entry to <xref:System.Printing.IndexedProperties.PrintProperty> and use it to create a <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
5.  <span data-ttu-id="a39aa-114">Ruft den Typ der der <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> aller der <xref:System.Printing.IndexedProperties.PrintProperty> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a39aa-114">Get the type of the <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> of each of the <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a><span data-ttu-id="a39aa-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a39aa-115">See also</span></span>
- <xref:System.Printing.IndexedProperties.PrintProperty>
- <xref:System.Printing.PrintSystemObject>
- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="a39aa-116">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="a39aa-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [<span data-ttu-id="a39aa-117">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="a39aa-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
