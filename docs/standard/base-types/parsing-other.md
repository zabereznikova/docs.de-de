---
title: Analysieren anderer Zeichenfolgen in .NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Char data type, parsing strings
- enumerations [.NET], parsing strings
- base types, parsing strings
- parsing strings, other strings
- Boolean data type, parsing strings
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
ms.openlocfilehash: 791ee37ff5f679d47492fc3cfdb61530bf570a36
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823991"
---
# <a name="parsing-other-strings-in-net"></a>Analysieren anderer Zeichenfolgen in .NET
Neben den numerischen und den <xref:System.DateTime>-Zeichenfolgen können Sie auch Zeichenfolgen in Datentypen analysieren, die die Typen <xref:System.Char>, <xref:System.Boolean> und <xref:System.Enum> darstellen.  
  
## <a name="char"></a>Char  
 Die statische Parse-Methode, die dem **Char**-Datentyp zugeordnet ist, eignet sich zum Konvertieren einer Zeichenfolge mit einem einzigen Zeichen in den entsprechenden Unicode-Wert. Im folgenden Codebeispiel wird eine Zeichenfolge in ein Unicode-Zeichen analysiert.  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a>Boolesch  
 Der **Boolean**-Datentyp enthält eine **Parse**-Methode, mit der Sie eine Zeichenfolge, die einen **-Wert darstellt, in einen tatsächlichen** -Typ konvertieren können. Diese Methode ist von der Groß-/Kleinschreibung unabhängig und kann erfolgreich eine Zeichenfolge mit „True“ oder „False“ analysieren. Die dem **Boolean**-Typ zugeordnete **Parse**-Methode kann auch Zeichenfolgen analysieren, die von Leerzeichen eingeschlossen sind. Wenn eine beliebige andere Zeichenfolge übergeben wird, wird eine <xref:System.FormatException> ausgelöst.  
  
 Im folgenden Codebeispiel wird die **Parse**-Methode zum Konvertieren einer Zeichenfolge in einen Boolean-Wert verwendet.  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a>Enumeration  
 Mit der statischen **Parse**-Methode können Sie einen Enumerationstyp auf den Wert einer Zeichenfolge initialisieren. Diese Methode akzeptiert den zu analysierenden Enumerationstyp, die zu analysierende Zeichenfolge und ein optionales Boolean-Flag, das angibt, ob bei der Analyse die Groß-/Kleinschreibung beachtet wird. Die zu analysierende Zeichenfolge kann mehrere durch Kommas voneinander getrennte Werte enthalten, denen ein oder mehrere Leerzeichen (auch als Leerräume bezeichnet) voran- oder nachgestellt sein können. Wenn die Zeichenfolge mehrere Werte enthält, entspricht der Wert des zurückgegebenen Objekts dem Wert aller angegebenen Werte, kombiniert mit einem bitweisen OR-Vorgang.  
  
 Im folgenden Beispiel wird die **Parse**-Methode zum Konvertieren einer Zeichenfolgendarstellung in einen Enumerationswert verwendet. Die <xref:System.DayOfWeek>-Enumeration wird über eine Zeichenfolge mit **Donnerstag** initialisiert.  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Analysieren von Zeichenfolgen](parsing-strings.md)
- [Formatierung von Typen](formatting-types.md)
- [Typkonvertierung in .NET](type-conversion.md)
