---
title: Windows Workflow Foundation-Glossar für .NET Framework 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Workflow Foundation [WF], glossary
- WF [WF], glossary
ms.assetid: ab682b2f-3779-45ca-b831-b7c03d7dbb3a
ms.openlocfilehash: 61d9acab1161302937e240eb8ebb506ca9f1585c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482846"
---
# <a name="windows-workflow-foundation-glossary-for-net-framework-45"></a>Windows Workflow Foundation-Glossar für .NET Framework 4.5

Die folgenden Begriffe werden in der Windows Workflow Foundation-Dokumentation verwendet.

## <a name="terms"></a>Begriffe

|Begriff|Definition|
|----------|----------------|
|Aktivität|Ein Programmverhalten in Windows Workflow Foundation. Einzelne Aktivitäten können zusammengesetzt werden, um komplexere Aktivitäten zu bilden.|
|Aktivitätsaktion|Eine Datenstruktur, die verwendet wird, um Rückrufe für die Workflow- und Aktivitätsausführung verfügbar zu machen.|
|argument|Definiert den eingehenden und ausgehenden Datenfluss einer Aktivität. Für jedes Argument ist eine Richtung angegeben: eingehend, ausgehend oder eingehend/ausgehend. Diese stellen die Eingabe-, Ausgabe- und Eingabe-/Ausgabeparameter der Aktivität dar.|
|bookmark|Der Punkt, an dem eine Aktivität angehalten werden und warten kann, bis die Wiederaufnahme erfolgt.|
|compensation|Eine Gruppe von Aktionen, die dazu vorgesehen sind, die Auswirkung der zuvor abgeschlossenen Arbeit rückgängig zu machen oder zu mildern.|
|Korrelation|Der Mechanismus zum Weiterleiten von Nachrichten an eine Workflow- oder Dienstinstanz.|
|Ausdruck|Ein Konstrukt, das eine oder mehrere Argumente akzeptiert, einen Vorgang unter Verwendung der Argumente durchführt und dann einen einzelnen Wert zurückgibt. Ausdrücke können überall dort verwendet werden, wo eine Aktivität verwendet werden kann.|
|Flussdiagramm|Ein bekanntes Modellierungsparadigma, das Programmkomponenten als Symbole darstellt, die mithilfe von Richtungspfeilen miteinander verknüpft sind.  In .NET Framework 4 können Workflows mithilfe der Flowchart-Aktivität als Flussdiagramme modelliert werden.|
|Prozess mit langer Laufzeit|Eine Einheit der Programmausführung, bei der keine sofortige Rückgabe erfolgt und die ggf. auch bei einem Systemneustart beibehalten wird.|
|Dauerhaftigkeit|Das Speichern des Zustands eines Workflows oder Diensts auf einem permanenten Speichermedium, sodass der Zustand nach einem Systemfehler aus dem Speicher entladen oder wiederhergestellt werden kann.|
|Zustandsautomat|Ein bekanntes Modellierungsparadigma, das Programmkomponenten als einzelne Zustände darstellt, die mithilfe von ereignisgesteuerten Zustandsübergängen miteinander verknüpft sind.  Workflows können mit der StateMachine-Aktivität als Zustandsautomaten modelliert werden.|
|Substanz|Stellt eine Gruppe von verwandten Lesezeichen unter einem gemeinsamen Bezeichner dar und ermöglicht der Runtime, Entscheidungen darüber zu treffen, ob eine bestimmte Lesezeichenwiederaufnahme gültig ist oder ungültig wird.|
|Typkonverter|Ein CLR-Typ kann einem oder mehreren abgeleiteten System.ComponentModel.TypeConverter-Typen zugeordnet werden, die das Konvertieren von Instanzen des CLR-Typs in und von Instanzen der anderen Typen ermöglicht. Ein Typkonverter wird mithilfe des System.ComponentModel.TypeConverterAttribute-Attributs einem CLR-Typ zugeordnet.  Ein TypeConverterAttribute kann direkt für den CLR-Typ oder für eine Eigenschaft festgelegt werden. Ein für eine Eigenschaft angegebener Typkonverter hat immer Vorrang vor einem Typkonverter, der für den CLR-Typ der Eigenschaft angegeben ist.|
|Variable|Stellt den Speicher einiger Daten dar, die später gespeichert werden müssen und auf die später zugegriffen werden muss.|
|Workflow|Eine einzelne Aktivität oder eine Struktur von Aktivitäten, die von einem Hostprozess aufgerufen wurde.|
|XAML|eXtensible Application Markup Language (XAML)|
