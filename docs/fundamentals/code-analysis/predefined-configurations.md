---
title: Vordefinierte Konfigurationsdateien (Code Analyse)
description: Erfahren Sie, wie Sie vordefinierte Editor config-und Regel Satz Dateien verwenden können, um bestimmte Arten der Code Analyse zu verwenden.
ms.date: 09/24/2020
ms.topic: conceptual
ms.openlocfilehash: 4937dcab1183fa3f63be4afc71627a7c7c08c6bd
ms.sourcegitcommit: 665f8fc55258356f4d2f4a6585b750c974b26675
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2020
ms.locfileid: "96591665"
---
# <a name="predefined-configuration-files"></a>Vordefinierte Konfigurationsdateien

Vordefinierte Editor config-und [Regel Satz](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) Dateien sind verfügbar, die es Ihnen ermöglichen, eine Kategorie von Code Qualitätsregeln, wie z. b. Sicherheits-oder Entwurfs Regeln, schnell und einfach zu aktivieren. Indem Sie eine bestimmte Kategorie von Regeln aktivieren, können Sie gezielte Probleme und bestimmte Bedingungen ermitteln. Um auf diese vordefinierten Dateien zuzugreifen, installieren Sie das nuget Analyzer-Paket [Microsoft. Code Analysis. netanalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) .

[Microsoft. Code Analysis. netanalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) enthält vordefinierte Editor config-Dateien und Regelsätze für die folgenden Regel Kategorien:

- Alle Regeln
- Datenfluss
- Entwurf
- Dokumentation
- Globalisierung
- Interoperabilität
- Wartbarkeit
- Benennung
- Leistung
- Portiert von FxCop
- Zuverlässigkeit
- Sicherheit
- Verbrauch

Jede dieser Kategorien von Regeln verfügt über eine Editor config-oder Regel Satz Datei für Folgendes:

- Alle Regeln in der Kategorie aktivieren (und alle anderen Regeln deaktivieren)
- Standard Schweregrad der Regel verwenden und standardmäßig aktiviert (und alle anderen Regeln deaktivieren)

> [!TIP]
> Die Kategorie "alle Regeln" verfügt über eine zusätzliche Editor config-oder Regel Satz Datei, um alle Regeln zu deaktivieren. Verwenden Sie diese Datei, um alle Analyse Warnungen oder-Fehler in einem Projekt schnell zu entfernen.

## <a name="predefined-editorconfig-files"></a>Vordefinierte Editor config-Dateien

Die vordefinierten Editor config-Dateien für das Microsoft. Code Analysis. netanalyzers Analyzer-Paket befinden sich im Unterverzeichnis " *Editor config* ", in dem das nuget-Paket installiert wurde. Beispielsweise befindet sich die Editor config-Datei, um alle Sicherheitsregeln zu aktivieren, unter *Editor config/securityrulesenabled/. Editor config*.

Kopieren Sie die ausgewählte *Editor config* -Datei in das Stammverzeichnis Ihres Projekts.

## <a name="predefined-rule-sets"></a>Vordefinierter Regelsatz

Die vordefinierten Regel Satz Dateien für das Microsoft. Code Analysis. netanalyzers Analyzer-Paket befinden sich im Unterverzeichnis *RuleSets* von, in dem das nuget-Paket installiert wurde. Beispielsweise befindet sich die Regel Satz Datei, um alle Sicherheitsregeln zu aktivieren, unter *RuleSets/securityrulesenabled. RuleSet*. Kopieren Sie mindestens einen Regelsatz, und fügen Sie ihn in das Verzeichnis ein, in dem sich das Projekt befindet.

## <a name="see-also"></a>Siehe auch

- [Analysetoolkonfiguration](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md)
- [Optionen für die .net-Codestil-Regel für Editor config](code-style-rule-options.md)
