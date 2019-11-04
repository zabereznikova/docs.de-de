---
title: 'Vorgehensweise: Indizierte Eigenschaften bei der COM-Interop-Programmierung – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 0d4e85646a1e7f8c4ee9a73fbf7bf5a01b10b14b
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423218"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a>Vorgehensweise: Indizierte Eigenschaften bei der COM-Interop-Programmierung (C#-Programmierhandbuch)
*Indizierte Eigenschaften* verbessern die Verarbeitung von COM-Eigenschaften mit Parametern in der C#-Programmierung. Indizierte Eigenschaften arbeiten zusammen mit anderen Funktionen in Visual C#, wie z.B. [benannte und optionale Argumente](../classes-and-structs/named-and-optional-arguments.md) und neuen Typinformationen ([dynamisch](../../language-reference/builtin-types/reference-types.md)) und [eingebettete Typinformationen](../../../standard/assembly/embed-types-visual-studio.md), um die Microsoft Office-Programmierung zu verbessern.  
  
 In früheren Versionen von C# waren Methoden nur als Eigenschaften zugänglich, wenn die `get`-Methode keine Parameter und die `set`-Methode nur einen Wertparameter hatte. Allerdings erfüllen nicht alle COM-Eigenschaften diese Einschränkungen. Die Eigenschaft <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> in Excel verfügt über eine `get`-Zugriffsmethode, für die ein Parameter für den Namen des Bereichs erforderlich ist. Früher mussten Sie stattdessen die `get_Range`-Methode verwenden, weil Sie nicht direkt auf die `Range`-Methode zugreifen konnten. Dies wird in folgendem Beispiel veranschaulicht.  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 Mit indizierte Eigenschaften können Sie stattdessen Folgendes schreiben:  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> Im vorherigen Beispiel wurde auch die Funktion [Optionale Argumente](../classes-and-structs/named-and-optional-arguments.md) verwendet, mit der Sie `Type.Missing` weglassen können.  
  
 Für das Festlegen der `Value`-Eigenschaft eines <xref:Microsoft.Office.Interop.Excel.Range>-Objekts in C# 3.0 und früher sind zwei Argumente erforderlich. Eines dieser Argumente stellt ein Argument für einen optionalen Parameter bereit, der den Typ des Bereichswerts angibt. Das andere Argument stellt den Wert für die `Value`-Eigenschaft bereit. In den folgenden Beispielen werden diese Techniken veranschaulicht. Beide legen den Wert der Zelle A1 auf `Name` fest.
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 Mit indizierte Eigenschaften können Sie stattdessen folgenden Code schreiben.  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 Sie können nicht Ihre eigenen indizierten Eigenschaften erstellen. Die Funktion unterstützt nur die Nutzung vorhandener indizierter Eigenschaften.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code veranschaulicht das vollständige Beispiel. Weitere Informationen zum Einrichten eines Projekts, das auf die Office-API zugreift, finden Sie unter [Vorgehensweise: Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen](./how-to-access-office-onterop-objects.md).  
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a>Siehe auch

- [Benannte und optionale Argumente](../classes-and-structs/named-and-optional-arguments.md)
- [dynamic](../../language-reference/builtin-types/reference-types.md)
- [Verwenden von dynamischen Typen](../types/using-type-dynamic.md)
- [Vorgehensweise: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [Vorgehensweise: Zugreifen auf Office-Interop-Objekte mithilfe von Visual C#-Funktionen](./how-to-access-office-onterop-objects.md)
- [Exemplarische Vorgehensweise: Office-Programmierung](./walkthrough-office-programming.md)
