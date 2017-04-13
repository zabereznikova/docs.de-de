---
title: "Analysieren von Zeichenfolgen in .NET Framework | Microsoft Docs"
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
  - "Analysieren von Zeichenfolgen, Informationen über das Analysieren von Zeichenfolgen"
  - "IFormatProvider-Schnittstelle, Analysieren von Zeichenfolgen"
  - "Basistypen, Analysieren von Zeichenfolgen"
  - "Parse-Methode"
  - "Analysieren von Zeichenfolgen"
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Analysieren von Zeichenfolgen in .NET Framework
Bei einem Analysevorgang wird eine Zeichenfolge, die einen .NET Framework\-Basistyp darstellt, in diesen Basistyp konvertiert.  Beispielsweise wird ein Analysevorgang verwendet, um eine Zeichenfolge in eine Gleitkommazahl oder in einen Datums\- und Uhrzeitwert zu konvertieren.  Für die Ausführung eines Analysevorgangs wird am häufigsten die `Parse`\-Methode verwendet.  Da es sich beim Analysieren um den Umkehrvorgang zum Formatieren \(wobei u. a. ein Basistyp in eine Zeichenfolgendarstellung umgewandelt wird\) handelt, gelten viele der gleichen Regeln und Konventionen.  Beim Formatieren wird ein Objekt verwendet, das die <xref:System.IFormatProvider>\-Schnittstelle implementiert, um kulturabhängige Formatierungsinformationen bereitzustellen. Entsprechend wird beim Analysieren ebenfalls ein Objekt verwendet, das die <xref:System.IFormatProvider>\-Schnittstelle implementiert, um zu bestimmen, wie eine Darstellung der Zeichenfolge interpretiert werden soll.  Weitere Informationen finden Sie unter [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md).  
  
## In diesem Abschnitt  
 [Verarbeiten numerischer Zeichenfolgen](../../../docs/standard/base-types/parsing-numeric.md)  
 Beschreibt das Konvertieren von Zeichenfolgen in numerische .NET Framework\-Typen.  
  
 [Verarbeiten von Zeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/parsing-datetime.md)  
 Beschreibt das Konvertieren von Zeichenfolgen in .NET Framework\-**DateTime**\-Typen.  
  
 [Verarbeiten anderer Zeichenfolgen](../../../docs/standard/base-types/parsing-other.md)  
 Beschreibt das Konvertieren von Zeichenfolgen in die Typen **Char**, **Boolean** und **Enum**.  
  
## Verwandte Abschnitte  
 [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)  
 Beschreibt grundlegende Formatierungskonzepte wie Formatbezeichner und Formatanbieter.  
  
 [Typkonvertierung in .NET Framework](../../../docs/standard/base-types/type-conversion.md)  
 Beschreibt das Konvertieren von Typen.  
  
 [Basistypen](../../../docs/standard/base-types/index.md)  
 Beschreibt gebräuchliche Operationen, die für .NET Framework\-Basistypen durchgeführt werden können.