---
title: Analysieren anderer Zeichenfolgen in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Char data type, parsing strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- parsing strings, other strings
- Boolean data type, parsing strings
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: edd48993f50ec8b91ba7941a682d7de9f22aa12e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-other-strings-in-net"></a>Analysieren anderer Zeichenfolgen in .NET
Zusätzlich zu den numerischen und <xref:System.DateTime> Zeichenfolgen, Sie können auch Analysieren von Zeichenfolgen, die die Typen darstellen <xref:System.Char>, <xref:System.Boolean>, und <xref:System.Enum> in Datentypen.  
  
## <a name="char"></a>Char  
 Die statische Parse-Methode, die dem **Char**-Datentyp zugeordnet ist, eignet sich zum Konvertieren einer Zeichenfolge mit einem einzigen Zeichen in den entsprechenden Unicode-Wert. Im folgenden Codebeispiel wird eine Zeichenfolge in ein Unicode-Zeichen analysiert.  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a>Boolesch  
 Die **booleschen** -Datentyp enthält eine **analysieren** -Methode, die Sie verwenden können, um eine Zeichenfolge zu konvertieren, die einen booleschen Wert in einen tatsächlichen darstellt **booleschen** Typ. Diese Methode ist von der Groß-/Kleinschreibung unabhängig und kann erfolgreich eine Zeichenfolge mit „True“ oder „False“ analysieren. Die **analysieren** zugeordnete Methode der **booleschen** Typ kann auch Analysieren von Zeichenfolgen, die durch Leerzeichen eingeschlossen sind. Wenn eine andere Zeichenfolge übergeben wird, eine <xref:System.FormatException> ausgelöst wird.  
  
 Im folgenden Codebeispiel wird mit der **analysieren** Methode zum Konvertieren einer Zeichenfolge in einen booleschen Wert.  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a>Enumeration  
 Mit der statischen **Parse**-Methode können Sie einen Enumerationstyp auf den Wert einer Zeichenfolge initialisieren. Diese Methode akzeptiert der Enumerationstyp, den Sie analysieren, die zu analysierende Zeichenfolge und ein optionales boolesches Flag, der angibt, ob die Analyse Groß-/Kleinschreibung beachtet wird. Die zu analysierende Zeichenfolge kann mehrere durch Kommas voneinander getrennte Werte enthalten, denen ein oder mehrere Leerzeichen (auch als Leerräume bezeichnet) voran- oder nachgestellt sein können. Wenn die Zeichenfolge mehrere Werte enthält, entspricht der Wert des zurückgegebenen Objekts dem Wert aller angegebenen Werte, kombiniert mit einem bitweisen OR-Vorgang.  
  
 Im folgenden Beispiel wird die **analysieren** Methode, um eine Zeichenfolgendarstellung in einen Enumerationswert zu konvertieren. Die <xref:System.DayOfWeek> Enumeration wird mit initialisiert **Donnerstag** aus einer Zeichenfolge.  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Analysieren von Zeichenfolgen](../../../docs/standard/base-types/parsing-strings.md)  
 [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)  
 [Typkonvertierung in .NET](../../../docs/standard/base-types/type-conversion.md)
