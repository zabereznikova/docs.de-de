---
title: Portabilität und Interoperabilitäts Regeln (Code Analyse)
description: Informationen zu Portabilität und Interoperabilitäts Regeln für die Code Analyse Regel
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.Portablityrules
- vs.codeanalysis.Interoperabilityrules
helpviewer_keywords:
- managed code analysis rules, interoperability rules, portability rules
- portability rules
- warnings, portability
- interoperability rules
- warnings, interoperability
author: gewarren
ms.author: gewarren
ms.openlocfilehash: a20cd77e13c4a8b95633d129990667f0a8de3ee8
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "96590683"
---
# <a name="portability-and-interoperability-rules"></a>Portabilitäts- und Interoperabilitätsregeln

Portabilitäts Regeln unterstützen Portabilität auf verschiedenen Plattformen Interoperabilitäts Regeln unterstützen Interaktionen mit com-Clients.

## <a name="in-this-section"></a>In diesem Abschnitt

| Regel | Beschreibung |
| - | - |
| [CA1401: P/Aufrufe dürfen nicht sichtbar sein.](ca1401.md) | Eine öffentliche oder geschützte Methode in einem öffentlichen Typ weist das System.Runtime.InteropServices.DllImportAttribute-Attribut auf (wird auch vom Declare-Schlüsselwort in Visual Basic implementiert). Solche Methoden sollten nicht verfügbar gemacht werden. |
| [CA1416: Plattformkompatibilität überprüfen](ca1416.md) | Durch die Verwendung von Platt Form abhängigen APIs in einer Komponente wird der Code nicht mehr auf allen Plattformen funktionieren. |
| [CA1417: nicht `OutAttribute` für Zeichen folgen Parameter für P/Aufrufe verwenden](ca1417.md) | Zeichen folgen Parameter, die mit dem als Wert übermittelt werden, `OutAttribute` können die Laufzeit destabilisieren, wenn die Zeichenfolge eine Internpool vorhanden Zeichenfolge ist. |
