---
title: Analysieren anderer Zeichenfolgen in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 08e891501bbefcf8b32eff10dd7294af9d81adac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127575"
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
  
## <a name="see-also"></a>Siehe auch

- [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)
- [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)
- [Typkonvertierung in .NET](../../../docs/standard/base-types/type-conversion.md)
