---
title: Erfassen von Telemetriedaten durch die ML.NET-CLI
description: Erfahren Sie mehr über die die Telemetriefeatures der ML.NET-CLI, die Nutzungsinformationen für die Analyse darüber erfassen, welche Daten gesammelt werden. Erfahren Sie auch, wie Sie diese Features deaktivieren können. Außerdem finden Sie hier Links zur .NET-Lizenzvereinbarung und Informationen zur Einhaltung der DSGVO durch Microsoft.
ms.topic: conceptual
ms.date: 05/05/2019
ms.custom: ''
ms.openlocfilehash: 49ebd6c9e1b77c85d891b8c9fb8cbd5c66b478a9
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065543"
---
# <a name="telemetry-collection-by-the-mlnet-cli"></a>Erfassen von Telemetriedaten durch die ML.NET-CLI

Die [ML.NET-CLI](http://aka.ms/mlnet-cli) beinhaltet ein Telemetriefeature, das anonyme Nutzungsdaten sammelt, die für die Verwendung durch Microsoft zusammengefasst werden.

## <a name="how-microsoft-uses-the-data"></a>So verwendet Microsoft die Daten

Das Produktteam verwendet die Telemetriedaten der ML.NET-CLI, um zu verstehen, wie die Tools verbessert werden können. Wenn Kunden beispielsweise eine bestimmte Machine Learning-Aufgabe selten nutzen, untersucht das Produktteam, warum dies der Fall ist, und verwendet die Ergebnisse, um die Entwicklung von Features zu priorisieren. Telemetriedaten der ML.NET-CLI unterstützen auch das Debugging von Problemen wie Abstürze und Codeanomalien. 

Das Produktteam schätzt diese Erkenntnis, aber wir wissen auch, dass nicht jeder diese Daten weitergeben möchte. [Erfahren Sie, wie Sie die Telemetriedaten deaktivieren können.](#opt-out-of-data-collection)

## <a name="scope"></a>Bereich

Der Befehl `mlnet` startet die ML.NET-CLI, aber die Befehl selbst sammelt noch keine Telemetriedaten.

Die Telemetrie wird durch die Ausführung des Befehls `mlnet` *nicht aktiviert*, wenn kein Befehl angefügt ist. Beispiel:

- `mlnet`
- `mlnet --help`

Die Telemetrie *wird aktiviert*, wenn Sie einen [ML.NET-CLI-Befehl](../reference/ml-net-cli-reference.md) ausführen, wie `mlnet auto-train`.

## <a name="opt-out-of-data-collection"></a>Ablehnen der Datensammlung

Die Telemetriefeature der ML.NET-CLI ist standardmäßig aktiviert.

Deaktivieren Sie die Telemetriefeature, indem Sie die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` auf `1` oder `true` festlegen. Diese Umgebungsvariable gilt global für das .NET CLI-Tool.

## <a name="data-points-collected"></a>Gesammelte Datenpunkte

Die Funktion sammelt die folgenden Daten:

- Welche Befehle aufgerufen werden, z.B. `auto-train`
- MAC-Adresse mit Hash: eine kryptografisch (SHA256) anonyme und eindeutige ID für einen Computer
- Zeitstempel eines Aufrufs
- Die aus drei Oktetten bestehende IP-Adresse, die nur zur Bestimmung des geografischen Standorts verwendet wird
- Die Namen aller verwendeter Argumente/Parameter Nicht die Kundenwerte, z.B. Zeichenfolgen
- Betriebssystem und Version
- Wert des ml-Task-Parameters: Kategoriewerte, z. B. `regression`, `binary-classification` und `multiclass-classification`
- Größe der [logarithmisch gerundeten](https://en.wikipedia.org/wiki/Rounding#Rounding_to_a_specified_power) Datasetdatei (nächste Potenz von 2)
- `ExitCode` des Befehls

Die Daten werden mithilfe der Technologie [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) sicher an die Microsoft-Server gesendet, unter eingeschränktem Zugriff gespeichert und unter strikter Sicherheitskontrolle durch die Systeme von [Azure Storage](https://azure.microsoft.com/services/storage/) verwendet.

### <a name="data-points-not-collected"></a>Nicht gesammelte Datenpunkte
Das Telemetriefeature sammelt *nicht*:
- persönliche Daten, z.B. Benutzernamen
- Namen der Datasetdateien
- Daten aus den Datasetdateien

Wenn Sie vermuten, dass durch die ML.NET-CLI-Telemetrie vertrauliche Daten gesammelt oder die Daten nicht sicher oder ordnungsgemäß behandelt werden, melden Sie ein Problem mit dem [ML.NET](https://github.com/dotnet/machinelearning)-Repository, damit dieses untersucht wird.

## <a name="license"></a>Lizenz

Die Microsoft-Verteilung der ML.NET-CLI ist gemäß den [Microsoft-Softwarelizenzbedingungen: Microsoft .NET-Bibliothek](https://aka.ms/dotnet-core-eula) lizenziert. Ausführlichere Informationen zur Datensammlung und -verarbeitung finden Sie im Abschnitt „Daten“.

## <a name="disclosure"></a>Offenlegung

Wenn Sie zum ersten Mal einen [ML.NET-CLI-Befehl](../reference/ml-net-cli-reference.md) wie `mlnet auto-train` ausführen, zeigt das ML.NET-CLI-Tool einen Text an, der Ihnen erklärt, wie Sie die Telemetrie deaktivieren können. Der Text kann abhängig von der von Ihnen ausgeführten Version der CLI leicht variieren.

## <a name="see-also"></a>Siehe auch
- [ML.NET-CLI-Referenz](../reference/ml-net-cli-reference.md)
- [Microsoft-Software-Lizenzbedingungen: Microsoft .NET-Bibliothek](https://aka.ms/dotnet-core-eula)
- [Datenschutz bei Microsoft](https://www.microsoft.com/en-us/trustcenter/privacy/)
- [Datenschutzerklärung von Microsoft](https://privacy.microsoft.com/en-us/privacystatement)
