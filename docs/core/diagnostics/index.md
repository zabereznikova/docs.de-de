---
title: Übersicht über Diagnosetools – .NET Core
description: Eine Übersicht über die Tools und Techniken, die zur Diagnose von .NET Core-Anwendungen zur Verfügung stehen.
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.topic: overview
ms.openlocfilehash: f107d15fa5584bb5a4834b5f11f1096bec7eb749
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974148"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a>Welche Diagnosetools sind in .NET Core verfügbar?

Software verhält sich nicht immer erwartungsgemäß, .NET Core verfügt jedoch über Tools und APIs, mit denen Sie diese Probleme schnell und effektiv diagnostizieren können.

Dieser Artikel hilft Ihnen bei der Suche nach den verschiedenen Tools, die Sie benötigen.

## <a name="managed-debuggersmanaged-debuggersmd"></a>[Verwaltete Debugger](managed-debuggers.md)
Verwaltete Debugger ermöglichen Ihnen die Interaktion mit dem Programm. Durch Anhalten, das inkrementelle Ausführen, Untersuchen und Fortsetzen erhalten Sie Erkenntnisse über das Verhalten Ihres Codes. Ein Debugger ist die erste Wahl für die Diagnose funktionaler Probleme, die leicht reproduziert werden können.

## <a name="logging-and-tracinglogging-tracingmd"></a>[Protokollierung und Ablaufverfolgung](logging-tracing.md)
Die Protokollierung und Ablaufverfolgung sind verwandte Techniken. Sie beziehen sich auf das Instrumentieren von Code zum Erstellen von Protokolldateien. In den Dateien werden die Details eines Programms aufgezeichnet. Diese Details können zur Diagnose der kompliziertesten Probleme verwendet werden. In Kombination mit Zeitstempeln sind diese Techniken auch für Leistungsuntersuchungen von Bedeutung.

## <a name="unit-testingtestingindexmd"></a>[Komponententests](../testing/index.md)
Komponententests sind eine wichtige Komponente von Continuous Integration und der Bereitstellung hochwertiger Software. Komponententests sollen Sie früh warnen, wenn Sie etwas unterbrechen.
