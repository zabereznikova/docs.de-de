---
title: Konvertieren von Zeichenfolgen in Typen
description: Machen Sie sich mit dem Analysieren von Zeichenfolgen in .NET vertraut. Beim Analysieren wird eine Zeichenfolge, die einen .NET-Basistyp darstellt, in diesen Basistyp konvertiert. Das Analysieren ist der entgegengesetzte Vorgang zum Formatieren.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: 3d23fa9c7ecc3593f03f70dbd5ea7bda841e8f4f
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400852"
---
# <a name="parse-strings-in-net"></a>Analysieren von Zeichenfolgen in .NET

Bei einem *Analysevorgang* wird eine Zeichenfolge, die einen .NET-Basistyp darstellt, in diesen Basistyp konvertiert. Beispielsweise wird ein Analysevorgang zum Konvertieren einer Zeichenfolge in eine Gleitkommazahl oder einen Wert für Datum und Uhrzeit verwendet. Die beim Ausführen eines Analysevorgangs am häufigsten verwendete Methode ist die `Parse`-Methode. Da die Analyse der umgekehrte Vorgang zur Formatierung (Konvertierung eines Basistyps in seine Zeichenfolgendarstellung) ist, gelten viele derselben Regeln und Konventionen. Ebenso, wie bei der Formatierung ein Objekt verwendet wird, das die <xref:System.IFormatProvider>-Schnittstelle zur Bereitstellung kulturabhängiger Formatierungsinformationen implementiert, wird auch bei der Analyse ein Objekt verwendet, das die <xref:System.IFormatProvider>-Schnittstelle zur Interpretation einer Zeichenfolgendarstellung implementiert. Weitere Informationen finden Sie unter [Formatieren von Typen](formatting-types.md).

## <a name="in-this-section"></a>In diesem Abschnitt
 [Analysieren numerischer Zeichenfolgen](parsing-numeric.md)\
 Beschreibt das Konvertieren von Zeichenfolgen in numerische .NET-Typen.

 [Analysieren von Zeichenfolgen für Datum und Uhrzeit](parsing-datetime.md)\
 Beschreibt das Konvertieren von Zeichenfolgen in **DateTime** -Typen in .NET.

 [Analysieren anderer Zeichenfolgen](parsing-other.md)\
 Beschreibt das Konvertieren von Zeichenfolgen in **Char** -, **Boolean** - und **Enum** -Typen.

## <a name="related-sections"></a>Verwandte Abschnitte
 [Formatierung von Typen](formatting-types.md)\
 Beschreibt grundlegende Formatierungsbegriffe wie „Formatbezeichner“ und „Formatanbieter“.

 [Typkonvertierung in .NET](type-conversion.md)\
 Beschreibt, wie Typen konvertiert werden.
