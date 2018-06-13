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
# <a name="how-to-get-print-system-object-properties-without-reflection"></a>Gewusst wie: Abrufen von Drucksystemobjekt-Eigenschaften ohne Reflektion
Mithilfe der Reflektion auf die Eigenschaften (und die Typen der Eigenschaften) für ein Objekt aufschlüsseln kann die Leistung der Anwendung beeinträchtigen. Die <xref:System.Printing.IndexedProperties> Namespace bietet eine Möglichkeit zum Abrufen dieser Informationen mit über Reflektion ermöglicht.  
  
## <a name="example"></a>Beispiel  
 Die Schritte hierzu sind wie folgt aus.  
  
1.  Erstellen Sie eine Instanz des Typs. Im folgenden Beispiel wird der Typ der <xref:System.Printing.PrintQueue> Typ, der Lieferumfang von Microsoft .NET Framework, jedoch nahezu identischen Code sollte für Typen, die Sie ableiten funktionieren <xref:System.Printing.PrintSystemObject>.  
  
2.  Erstellen einer <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> aus des Typs <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>. Die <xref:System.Collections.DictionaryEntry.Value%2A> für jeden Eintrag in dieses Wörterbuch aufweist und ein Objekt ist eines von abgeleiteten Typen <xref:System.Printing.IndexedProperties.PrintProperty>.  
  
3.  Zählt die Elemente des Wörterbuchs. Für jede von ihnen die folgenden Schritte aus.  
  
4.  Nach-oben-wandeln Sie den Wert jedes Eintrags in <xref:System.Printing.IndexedProperties.PrintProperty> und verwenden sie zum Erstellen einer <xref:System.Printing.IndexedProperties.PrintProperty> Objekt.  
  
5.  Ruft den Typ der der <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> aller der <xref:System.Printing.IndexedProperties.PrintProperty> Objekt.  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Printing.IndexedProperties.PrintProperty>  
 <xref:System.Printing.PrintSystemObject>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)
