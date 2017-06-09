---
title: "Analysieren anderer Zeichenfolgen in .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Char-Datentyp, Analysieren von Zeichenfolgen"
  - "Enumerationen [.NET Framework-Profilerstellung], Analysieren von Zeichenfolgen"
  - "Basistypen, Analysieren von Zeichenfolgen"
  - "Analysieren von Zeichenfolgen, sonstige Zeichenfolgen"
  - "Boolean-Datentyp, Analysieren von Zeichenfolgen"
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Analysieren anderer Zeichenfolgen in .NET Framework
Neben numerischen und <xref:System.DateTime>\-Zeichenfolgen können Sie auch Zeichenfolgen zu Datentypen verarbeiten, die die Typen <xref:System.Char>, <xref:System.Boolean> und <xref:System.Enum> darstellen.  
  
## Char  
 Die dem Datentyp **Char** zugeordnete statische Parse\-Methode eignet sich zum Konvertieren von Zeichenfolgen, die aus einem einzigen Zeichen bestehen, in den entsprechenden Unicode\-Wert.  Im folgenden Codebeispiel wird eine Zeichenfolge zu einem Unicode\-Zeichen verarbeitet.  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## Boolean  
 Der Datentyp **Boolean** enthält eine **Parse**\-Methode, die sich zum Konvertieren einer Zeichenfolge, die einen booleschen Wert darstellt, in einen tatsächlichen **Boolean**\-Typ eignet.  Bei dieser Methode wird Groß\-\/Kleinschreibung nicht beachtet. Mit ihr können problemlos Zeichenfolgen verarbeitet werden, die "True" oder "False" enthalten. Die dem **Boolean**\-Typ zugeordnete **Parse**\-Methode kann auch Zeichenfolgen verarbeiten, die von Leerzeichen eingeschlossen sind.  Bei Übergabe einer anderen Zeichenfolge wird eine <xref:System.FormatException> ausgelöst.  
  
 Im folgenden Beispielcode wird eine Zeichenfolge unter Verwendung der **Parse**\-Methode in einen booleschen Wert konvertiert.  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## Enumeration  
 Sie können die statische **Parse**\-Methode verwenden, um einen Enumerationstyp mit einem Zeichenfolgenwert zu initialisieren.  Diese Methode akzeptiert den verarbeiteten Enumerationstyp, die zu verarbeitende Zeichenfolge und ein optionales Boolean\-Flag, das festlegt, ob Groß\- und Kleinschreibung beachtet wird oder nicht.  Die verarbeitete Zeichenfolge kann verschiedene, durch Kommas getrennte Werte enthalten; diesen Werten kann eine beliebige Anzahl von Leerzeichen voran\- oder nachgestellt sein.  Enthält die Zeichenfolge mehrere Werte, ist der Wert des zurückgegebenen Objekts das Ergebnis einer bitweisen ODER\-Verknüpfung aller angegebenen Werte.  
  
 Im folgenden Codebeispiel wird eine Zeichenfolgenentsprechung unter Verwendung der **Parse**\-Methode in einen Enumerationswert konvertiert.  Die <xref:System.DayOfWeek>\-Enumeration wird durch eine Zeichenfolge mit **Thursday** initialisiert.  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## Siehe auch  
 [Analysieren von Zeichenfolgen](../../../docs/standard/base-types/parsing-strings.md)   
 [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)   
 [Typkonvertierung in .NET Framework](../../../docs/standard/base-types/type-conversion.md)