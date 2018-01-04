---
title: 'Gewusst wie: Abrufen von Drucksystemobjekt-Eigenschaften ohne Reflektion'
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
helpviewer_keywords: PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d93919f691b51d5f177b074e5d9cef2c140458e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a><span data-ttu-id="dac3d-102">Gewusst wie: Abrufen von Drucksystemobjekt-Eigenschaften ohne Reflektion</span><span class="sxs-lookup"><span data-stu-id="dac3d-102">How to: Get Print System Object Properties Without Reflection</span></span>
<span data-ttu-id="dac3d-103">Mithilfe der Reflektion auf die Eigenschaften (und die Typen der Eigenschaften) für ein Objekt aufschlüsseln kann die Leistung der Anwendung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="dac3d-103">Using reflection to itemize the properties (and the types of those properties) on an object can slow application performance.</span></span> <span data-ttu-id="dac3d-104">Die <xref:System.Printing.IndexedProperties> Namespace bietet eine Möglichkeit zum Abrufen dieser Informationen mit über Reflektion ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="dac3d-104">The <xref:System.Printing.IndexedProperties> namespace provides a means to getting this information with using reflection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dac3d-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dac3d-105">Example</span></span>  
 <span data-ttu-id="dac3d-106">Die Schritte hierzu sind wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="dac3d-106">The steps for doing this are as follows.</span></span>  
  
1.  <span data-ttu-id="dac3d-107">Erstellen Sie eine Instanz des Typs.</span><span class="sxs-lookup"><span data-stu-id="dac3d-107">Create an instance of the type.</span></span> <span data-ttu-id="dac3d-108">Im folgenden Beispiel wird der Typ der <xref:System.Printing.PrintQueue> Typ, der im Lieferumfang [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], aber nahezu identischer Code sollte für Typen, die Sie ableiten funktionieren <xref:System.Printing.PrintSystemObject>.</span><span class="sxs-lookup"><span data-stu-id="dac3d-108">In the example below, the type is the <xref:System.Printing.PrintQueue> type that ships with [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], but nearly identical code should work for types that you derive from <xref:System.Printing.PrintSystemObject>.</span></span>  
  
2.  <span data-ttu-id="dac3d-109">Erstellen einer <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> aus des Typs <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="dac3d-109">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the type's <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span></span> <span data-ttu-id="dac3d-110">Die <xref:System.Collections.DictionaryEntry.Value%2A> für jeden Eintrag in dieses Wörterbuch aufweist und ein Objekt ist eines von abgeleiteten Typen <xref:System.Printing.IndexedProperties.PrintProperty>.</span><span class="sxs-lookup"><span data-stu-id="dac3d-110">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span>  
  
3.  <span data-ttu-id="dac3d-111">Zählt die Elemente des Wörterbuchs.</span><span class="sxs-lookup"><span data-stu-id="dac3d-111">Enumerate the members of the dictionary.</span></span> <span data-ttu-id="dac3d-112">Für jede von ihnen die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="dac3d-112">For each of them, do the following.</span></span>  
  
4.  <span data-ttu-id="dac3d-113">Nach-oben-wandeln Sie den Wert jedes Eintrags in <xref:System.Printing.IndexedProperties.PrintProperty> und verwenden sie zum Erstellen einer <xref:System.Printing.IndexedProperties.PrintProperty> Objekt.</span><span class="sxs-lookup"><span data-stu-id="dac3d-113">Up-cast the value of each entry to <xref:System.Printing.IndexedProperties.PrintProperty> and use it to create a <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
5.  <span data-ttu-id="dac3d-114">Ruft den Typ der der <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> aller der <xref:System.Printing.IndexedProperties.PrintProperty> Objekt.</span><span class="sxs-lookup"><span data-stu-id="dac3d-114">Get the type of the <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> of each of the <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a><span data-ttu-id="dac3d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dac3d-115">See Also</span></span>  
 <xref:System.Printing.IndexedProperties.PrintProperty>  
 <xref:System.Printing.PrintSystemObject>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [<span data-ttu-id="dac3d-116">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="dac3d-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="dac3d-117">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="dac3d-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
