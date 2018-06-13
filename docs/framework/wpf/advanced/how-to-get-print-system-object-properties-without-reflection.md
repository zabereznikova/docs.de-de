---
title: 'Gewusst wie: Abrufen von Drucksystemobjekt-Eigenschaften ohne Reflektion'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
ms.openlocfilehash: 1fa8029b8245aef5e10e9082a1038fd89fc1c84e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544729"
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a><span data-ttu-id="d3bf5-102">Gewusst wie: Abrufen von Drucksystemobjekt-Eigenschaften ohne Reflektion</span><span class="sxs-lookup"><span data-stu-id="d3bf5-102">How to: Get Print System Object Properties Without Reflection</span></span>
<span data-ttu-id="d3bf5-103">Mithilfe der Reflektion auf die Eigenschaften (und die Typen der Eigenschaften) für ein Objekt aufschlüsseln kann die Leistung der Anwendung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="d3bf5-103">Using reflection to itemize the properties (and the types of those properties) on an object can slow application performance.</span></span> <span data-ttu-id="d3bf5-104">Die <xref:System.Printing.IndexedProperties> Namespace bietet eine Möglichkeit zum Abrufen dieser Informationen mit über Reflektion ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="d3bf5-104">The <xref:System.Printing.IndexedProperties> namespace provides a means to getting this information with using reflection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3bf5-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d3bf5-105">Example</span></span>  
 <span data-ttu-id="d3bf5-106">Die Schritte hierzu sind wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="d3bf5-106">The steps for doing this are as follows.</span></span>  
  
1.  <span data-ttu-id="d3bf5-107">Erstellen Sie eine Instanz des Typs.</span><span class="sxs-lookup"><span data-stu-id="d3bf5-107">Create an instance of the type.</span></span> <span data-ttu-id="d3bf5-108">Im folgenden Beispiel wird der Typ der <xref:System.Printing.PrintQueue> Typ, der Lieferumfang von Microsoft .NET Framework, jedoch nahezu identischen Code sollte für Typen, die Sie ableiten funktionieren <xref:System.Printing.PrintSystemObject>.</span><span class="sxs-lookup"><span data-stu-id="d3bf5-108">In the example below, the type is the <xref:System.Printing.PrintQueue> type that ships with Microsoft .NET Framework, but nearly identical code should work for types that you derive from <xref:System.Printing.PrintSystemObject>.</span></span>  
  
2.  <span data-ttu-id="d3bf5-109">Erstellen einer <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> aus des Typs <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3bf5-109">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the type's <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span></span> <span data-ttu-id="d3bf5-110">Die <xref:System.Collections.DictionaryEntry.Value%2A> für jeden Eintrag in dieses Wörterbuch aufweist und ein Objekt ist eines von abgeleiteten Typen <xref:System.Printing.IndexedProperties.PrintProperty>.</span><span class="sxs-lookup"><span data-stu-id="d3bf5-110">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span>  
  
3.  <span data-ttu-id="d3bf5-111">Zählt die Elemente des Wörterbuchs.</span><span class="sxs-lookup"><span data-stu-id="d3bf5-111">Enumerate the members of the dictionary.</span></span> <span data-ttu-id="d3bf5-112">Für jede von ihnen die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="d3bf5-112">For each of them, do the following.</span></span>  
  
4.  <span data-ttu-id="d3bf5-113">Nach-oben-wandeln Sie den Wert jedes Eintrags in <xref:System.Printing.IndexedProperties.PrintProperty> und verwenden sie zum Erstellen einer <xref:System.Printing.IndexedProperties.PrintProperty> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d3bf5-113">Up-cast the value of each entry to <xref:System.Printing.IndexedProperties.PrintProperty> and use it to create a <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
5.  <span data-ttu-id="d3bf5-114">Ruft den Typ der der <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> aller der <xref:System.Printing.IndexedProperties.PrintProperty> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d3bf5-114">Get the type of the <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> of each of the <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a><span data-ttu-id="d3bf5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3bf5-115">See Also</span></span>  
 <xref:System.Printing.IndexedProperties.PrintProperty>  
 <xref:System.Printing.PrintSystemObject>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [<span data-ttu-id="d3bf5-116">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="d3bf5-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="d3bf5-117">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="d3bf5-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
