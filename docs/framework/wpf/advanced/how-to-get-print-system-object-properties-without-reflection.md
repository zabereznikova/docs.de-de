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
# <a name="how-to-get-print-system-object-properties-without-reflection"></a>Vorgehensweise: Abrufen von Drucksystemobjekt-Eigenschaften ohne Reflektion
Mithilfe von Reflektion zum aufschlüsseln von Eigenschaften (und die Typen der Eigenschaften) für ein Objekt kann die Leistung der Anwendung beeinträchtigen. Die <xref:System.Printing.IndexedProperties> Namespace bietet eine Möglichkeit zum Abrufen dieser Informationen mit der Verwendung von Reflektion.  
  
## <a name="example"></a>Beispiel  
 Die Schritte dazu sind wie folgt aus.  
  
1.  Erstellen Sie eine Instanz des Typs. Im folgenden Beispiel wird der Typ ist der <xref:System.Printing.PrintQueue> Typ, der in Microsoft .NET Framework, aber nahezu identischen Code enthalten ist, sollte für Typen, die Sie eine Ableitung aus funktionieren <xref:System.Printing.PrintSystemObject>.  
  
2.  Erstellen Sie eine <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> aus des Typs des <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>. Die <xref:System.Collections.DictionaryEntry.Value%2A> -Eigenschaft für jeden Eintrag in diesem Wörterbuch ist ein Objekt vom Typ abgeleitet <xref:System.Printing.IndexedProperties.PrintProperty>.  
  
3.  Auflisten der Elemente des Wörterbuchs. Führen Sie die folgenden Schritte aus, für jede von diesen.  
  
4.  Nach-oben-wandeln Sie den Wert jedes Eintrags in <xref:System.Printing.IndexedProperties.PrintProperty> und verwenden sie zum Erstellen einer <xref:System.Printing.IndexedProperties.PrintProperty> Objekt.  
  
5.  Ruft den Typ der der <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> aller der <xref:System.Printing.IndexedProperties.PrintProperty> Objekt.  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Printing.IndexedProperties.PrintProperty>
- <xref:System.Printing.PrintSystemObject>
- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)
