---
title: Dokumentations Regeln (Code Analyse)
description: Informationen zu den Dokumentations Regeln für die Code Analyse Regel
ms.date: 09/16/2019
ms.topic: reference
f1_keywords:
- vs.codeanalysis.documentationrules
helpviewer_keywords:
- documentation rules
- managed code analysis rules, documentation rules
- warnings, documentation
author: mavasani
ms.author: mavasani
ms.openlocfilehash: 29d1734eec29bd00d456b4b00c48c2e8ef223441
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "96590768"
---
# <a name="documentation-rules"></a>Dokumentationsregeln

Dokumentations Regeln unterstützen das Schreiben von gut dokumentierten Bibliotheken durch die korrekte Verwendung von [XML-Dokumentations Kommentaren](../../../csharp/codedoc.md) für extern sichtbare APIs.

## <a name="in-this-section"></a>In diesem Abschnitt

| Regel | Beschreibung |
| - | - |
| [CA1200: Verwenden Sie keine cref-Tags mit einem Präfix.](ca1200.md) | Das Attribut " [kref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) " in einem XML-Dokumenttag bedeutet "Code Verweis". Es gibt an, dass der innere Text des Tags ein Codeelement ist, wie z.B. ein Typ, eine Methode oder Eigenschaft. Vermeiden `cref` Sie die Verwendung von Tags mit Präfixen, da dies verhindert, dass der Compiler Verweise überprüft. Außerdem wird verhindert, dass die integrierte Entwicklungsumgebung (IDE) von Visual Studio diese Symbol Verweise bei refactoren findet und aktualisiert. |
