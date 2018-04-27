---
title: 'Gewusst wie: Abrufen von Drucksystemobjekt-Eigenschaften ohne Reflektion'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f1aa6025c2b8a00dd170a674a1bdea25d76a9a1
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
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
