---
title: Analysieren von Zeichenfolgen in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9c2193dd1b1f3c0478efb5fc9c2b80250ef1878f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
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
