---
title: Nicht benötigte Coderegeln
description: Erfahren Sie mehr über die Code Analyse für unnötige Code Regeln.
ms.date: 09/30/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
ms.openlocfilehash: 16c4ba0e4bee2388736bf9813a3e8290d8d4da32
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "96592019"
---
# <a name="unnecessary-code-rules"></a>Nicht benötigte Coderegeln

Unnötige Code Regeln identifizieren verschiedene Teile der Codebasis, die unnötig sind und umfaciert oder entfernt werden können. Das vorhanden sein von unnötigem Code weist auf eines der folgenden Probleme hin:

- Lesbarkeit: Code, der eine unnötige Herabwürdigung der Lesbarkeit ermöglicht. [IDE0001](ide0001.md) Flags beispielsweise überflüssige Typnamens Qualifizierungen.
- Wartbarkeit: Code, der nach dem Refactoring nicht mehr verwendet wird und unnötigerweise gewartet wird. [IDE0051](ide0051.md) Flags z. b. nicht verwendete private Felder, Eigenschaften, Ereignisse und Methoden.
- Leistung: unnötige Berechnung, die keine Nebenwirkungen hat und zu unnötigem Leistungs Aufwand führt. [IDE0059](ide0059.md) Flags z. b. nicht verwendete Wert Zuweisungen, bei denen der Ausdruck zum Berechnen eines Werts keine Nebeneffekte hat.
- Funktionalität: funktionales Problem im Code, das dazu führt, dass erforderlicher Code redundant ist. [IDE0060](ide0060.md) Flags z. b. nicht verwendete Parameter, bei denen die Methode versehentlich einen Eingabeparameter ignoriert.

Die Regeln in diesem Abschnitt betreffen die folgenden unnötigen Code Regeln:

- [Name vereinfachen (IDE0001)](ide0001.md)
- [Vereinfachen des Mitglieds Zugriffs (IDE0002)](ide0002.md)
- [Unnötige Umwandlung entfernen (IDE0004)](ide0004.md)
- [Unnötigen Import entfernen (IDE0005)](ide0005.md)
- [Entfernen von nicht erreichbarem Code (IDE0035)](ide0035.md)
- [Nicht verwendeten privaten Member entfernen (IDE0051)](ide0051.md)
- [Nicht gelesene private Member entfernen (IDE0052)](ide0052.md)
- [Nicht verwendeten Ausdruckswert entfernen (IDE0058)](ide0058.md)
- [Unnötige Wert Zuweisung entfernen (IDE0059)](ide0059.md)
- [Nicht verwendeten Parameter entfernen (IDE0060)](ide0060.md)
- [Unnötige Unterdrückung entfernen (IDE0079)](ide0079.md)
- [Entfernen Sie den unnötigen Unterdrückungs Operator (IDE0080)](ide0080.md) nur c#.
- [Entfernen Sie "ByVal" (IDE0081)](ide0081.md) nur Visual Basic.
- [Unnötigen Gleichheits Operator entfernen (IDE0100)](ide0100.md)
- [Entfernen Sie unnötige verwerfen (IDE0110)](ide0110.md) nur c#.

Einige dieser Regeln verfügen über Optionen zum Konfigurieren des Regel Verhaltens:

- [csharp_style_unused_value_expression_statement_preference (IDE0058)](ide0058.md#csharp_style_unused_value_expression_statement_preference)
- [visual_basic_style_unused_value_expression_statement_preference (IDE0058)](ide0058.md#visual_basic_style_unused_value_expression_statement_preference)
- [csharp_style_unused_value_assignment_preference (IDE0059)](ide0059.md#csharp_style_unused_value_assignment_preference)
- [visual_basic_style_unused_value_assignment_preference (IDE0059)](ide0059.md#visual_basic_style_unused_value_assignment_preference)
- [dotnet_code_quality_unused_parameters (IDE0060)](ide0060.md#dotnet_code_quality_unused_parameters)
- [dotnet_remove_unnecessary_suppression_exclusions (IDE0079)](ide0079.md#dotnet_remove_unnecessary_suppression_exclusions)

## <a name="see-also"></a>Siehe auch

- [Regeln für Code Stilsprache](language-rules.md)
- [Codestil-Regel Referenz](index.md)
