---
title: Analysieren von Zeichenfolgen in .NET
description: Analysieren von Zeichenfolgen in .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 8103c0a6-61d3-40dd-a3e9-2a32ba6a4c05
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: c741ae793d491f691a355df6ad064b81d609c7e5
ms.lasthandoff: 03/03/2017

---

# <a name="parsing-strings-in-net"></a>Analysieren von Zeichenfolgen in .NET

Bei einem Analysevorgang wird eine Zeichenfolge, die einen .NET-Basistyp darstellt, in diesen Basistyp konvertiert. Beispielsweise wird ein Analysevorgang zum Konvertieren einer Zeichenfolge in eine Gleitkommazahl oder einen Wert für Datum und Uhrzeit verwendet. Die beim Ausführen eines Analysevorgangs am häufigsten verwendete Methode ist die `Parse`-Methode. Da die Analyse der umgekehrte Vorgang zur Formatierung (Konvertierung eines Basistyps in seine Zeichenfolgendarstellung) ist, gelten viele derselben Regeln und Konventionen. Ebenso, wie bei der Formatierung ein Objekt verwendet wird, das die [IFormatProvider](xref:System.IFormatProvider)-Schnittstelle zur Bereitstellung kulturabhängiger Formatierungsinformationen implementiert, wird auch bei der Analyse ein Objekt verwendet, das die [IFormatProvider](xref:System.IFormatProvider)-Schnittstelle implementiert, um zu ermitteln, wie eine Zeichenfolgendarstellung zu interpretieren ist. Weitere Informationen finden Sie unter [Formatieren von Typen in .NET](formatting-types.md).

## <a name="in-this-section"></a>In diesem Abschnitt

[Analysieren numerischer Zeichenfolgen in .NET](parsing-numeric.md): Beschreibt das Konvertieren von Zeichenfolgen in numerische .NET-Typen.

[Analysieren von Zeichenfolgen für Datum und Uhrzeit in .NET](parsing-datetime.md): Beschreibt das Konvertieren von Zeichenfolgen in .NET-`DateTime`-Typen.

[Analysieren anderer Zeichenfolgen in .NET](parsing-other.md): Beschreibt das Konvertieren von Zeichenfolgen in die Typen [Char](xref:System.Char), [Boolean](xref:System.Boolean) und [Enum](xref:System.Enum).

[Formatieren von Typen in .NET](formatting-types.md): Beschreibt grundlegende Formatierungskonzepte wie Formatbezeichner und Formatanbieter.

[Typkonvertierung in .NET](type-conversion.md): Beschreibt die Konvertierung von Typen.

[Arbeiten mit Basistypen in .NET](index.md): Beschreibt allgemeine Vorgänge, die für .NET-Basistypen ausgeführt werden können.


