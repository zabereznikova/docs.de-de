---
title: Globalisierungsregeln (Code Analyse)
description: Informationen zu Globalisierungsregeln für die Code Analyse Regel
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.globalizationrules
helpviewer_keywords:
- rules, globalization
- globalization rules
- globalization [Visual Studio], rules
- managed code analysis rules, globalization rules
author: gewarren
ms.author: gewarren
ms.openlocfilehash: 83ecc52c5e20e074c6c1aed68204a574494f42d5
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "96591594"
---
# <a name="globalization-rules"></a>Globalisierungsregeln

Globalisierungsregeln unterstützen weltweit bereite Bibliotheken und Anwendungen.

## <a name="in-this-section"></a>In diesem Abschnitt

|Regel|Beschreibung|
|----------|-----------------|
|[CA1303: Literale nicht als lokalisierte Parameter übergeben.](ca1303.md)|Eine extern sichtbare Methode übergibt ein Zeichenfolgenliteralzeichen als Parameter an einen .net-Konstruktor oder eine Methode, und diese Zeichenfolge muss lokalisierbar sein.|
|[CA1304: CultureInfo angeben.](ca1304.md)|Eine Methode oder ein Konstruktor ruft einen Member mit einer Überladung auf, die einen System.Globalization.CultureInfo-Parameter akzeptiert. Die Methode oder der Konstruktor ruft nicht die Überladung auf, die den CultureInfo-Parameter akzeptiert. Wenn ein CultureInfo-Objekt oder ein System.IFormatProvider-Objekt nicht angegeben wird, besitzt der vom überladenen Member bereitgestellte Standardwert möglicherweise nicht in allen Gebietsschemas den gewünschten Effekt.|
|[CA1305: IFormatProvider angeben.](ca1305.md)|Eine Methode oder ein Konstruktor ruft einen oder mehrere Member auf, die Überladungen besitzen und einen System.IFormatProvider-Parameter akzeptieren; die Methode oder der Konstruktor ruft die Überladung nicht auf, die den IFormatProvider-Parameter akzeptiert. Wenn ein System.Globalization.CultureInfo-Objekt oder ein IFormatProvider-Objekt nicht angegeben wird, besitzt der vom überladenen Member bereitgestellte Standardwert möglicherweise nicht in allen Gebietsschemas den gewünschten Effekt.|
|[CA1307: "StringComparison" zur Verdeutlichung angeben](ca1307.md)|Ein Zeichenfolgenvergleich verwendet eine Methodenüberladung, durch die kein StringComparison-Parameter festgelegt wird.|
|[CA1308: Zeichenfolgen in Großbuchstaben normalisieren.](ca1308.md)|Zeichenfolgen sollten in Großschreibung normalisiert werden. Für eine kleine Gruppe von Zeichen wird bei der Konvertierung in Kleinbuchstaben kein Roundtrip ausgeführt.|
|[CA1309: Ordinal-StringComparison verwenden.](ca1309.md)|Durch einen nicht linguistischen Zeichenfolgenvergleich wird der StringComparison-Parameter nicht auf Ordinal und nicht auf OrdinalIgnoreCase festgelegt. Wenn der Parameter explizit auf StringComparison.Ordinal oder StringComparison.OrdinalIgnoreCase festgelegt wird, werden die Codeausführung beschleunigt sowie Richtigkeit und Zuverlässigkeit gesteigert.|
|[CA1310: "StringComparison" für Richtigkeit angeben](ca1310.md)|Eine Zeichen folgen Vergleichsoperation verwendet eine Methoden Überladung, die keinen StringComparison-Parameter festgelegt und standardmäßig einen kulturspezifischen Zeichen folgen Vergleich verwendet.|
|[CA2101: Marshalling für P/Aufruf-Zeichen folgen Argumente angeben](ca2101.md)|Ein Platt Form Aufruf-Member ermöglicht teilweise vertrauenswürdigen Aufrufern, verfügt über einen Zeichen folgen Parameter und führt die Zeichenfolge nicht explizit aus. Auf diese Weise kann potenziell eine Sicherheitslücke verursacht werden.|
