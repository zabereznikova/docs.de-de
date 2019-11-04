---
title: Analysieren von Zeichenfolgen in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: e4bf14981e538d95aebac3b0f36d38b61747989f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084316"
---
# <a name="parsing-strings-in-net"></a>Analysieren von Zeichenfolgen in .NET
Bei einem Analysevorgang wird eine Zeichenfolge, die einen .NET-Basistyp darstellt, in diesen Basistyp konvertiert. Beispielsweise wird ein Analysevorgang zum Konvertieren einer Zeichenfolge in eine Gleitkommazahl oder einen Wert für Datum und Uhrzeit verwendet. Die beim Ausführen eines Analysevorgangs am häufigsten verwendete Methode ist die `Parse`-Methode. Da die Analyse der umgekehrte Vorgang zur Formatierung (Konvertierung eines Basistyps in seine Zeichenfolgendarstellung) ist, gelten viele derselben Regeln und Konventionen. Ebenso, wie bei der Formatierung ein Objekt verwendet wird, das die <xref:System.IFormatProvider>-Schnittstelle zur Bereitstellung kulturabhängiger Formatierungsinformationen implementiert, wird auch bei der Analyse ein Objekt verwendet, das die <xref:System.IFormatProvider>-Schnittstelle zur Interpretation einer Zeichenfolgendarstellung implementiert. Weitere Informationen finden Sie unter [Formatieren von Typen in .NET](../../../docs/standard/base-types/formatting-types.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Verarbeiten numerischer Zeichenfolgen](../../../docs/standard/base-types/parsing-numeric.md)  
 Beschreibt das Konvertieren von Zeichenfolgen in numerische .NET-Typen.  
  
 [Verarbeiten von Zeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/parsing-datetime.md)  
 Beschreibt das Konvertieren von Zeichenfolgen in **DateTime**-Typen in .NET.  
  
 [Verarbeiten anderer Zeichenfolgen](../../../docs/standard/base-types/parsing-other.md)  
 Beschreibt das Konvertieren von Zeichenfolgen in **Char**-, **Boolean**- und **Enum**-Typen.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)  
 Beschreibt grundlegende Formatierungsbegriffe wie „Formatbezeichner“ und „Formatanbieter“.  
  
 [Typkonvertierung in .NET](../../../docs/standard/base-types/type-conversion.md)  
 Beschreibt, wie Typen konvertiert werden.  
  
 [Basistypen](../../../docs/standard/base-types/index.md)  
 Beschreibt allgemeine Vorgänge, die für .NET-Basistypen ausgeführt werden können.
