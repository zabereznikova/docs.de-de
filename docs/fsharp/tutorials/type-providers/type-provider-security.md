---
title: Sicherheit von Typanbietern
description: "Informationen Sie zur Sicherheit von typanbietern in f#, einschließlich Informationen zum Ändern der Einstellungen für einen Typanbieter für die Vertrauensstellung."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9c5a8a1f-5a31-490d-83c0-8beabda75c78
ms.openlocfilehash: c8f03ee90d4dce1d3484a9dfe8951d500d509a2b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="type-provider-security"></a>Sicherheit von Typanbietern

Typanbieter sind Assemblys (DLLs) auf dem f#-Projekt oder das Skript verweist, die Code enthalten, um eine Verbindung mit externen Datenquellen herstellen und diese Typinformationen Oberfläche, mit der F#-Typ-Umgebung. In der Regel wird Code in Assemblys, auf die verwiesen wird nur ausgeführt, beim Kompilieren und dann führen Sie den Code (oder im Falle eines Skripts den Code an f# Interactive senden). Eine typanbieterassembly wird jedoch innerhalb von Visual Studio ausgeführt werden, wenn der Code im Editor lediglich durchsucht wird. Dies liegt daran, dass Typanbieter müssen ausführen, um zusätzliche Informationen in den Editor, z. B. QuickInfos, IntelliSense-Beendigungen hinzufügen und so weiter. Daher sind zusätzliche sicherheitsüberlegungen für den Typ Anbieterassemblys vorhanden, da diese automatisch in Visual Studio-Prozess ausgeführt werden.


## <a name="security-warning-dialog"></a>Warnung-Dialogfeld "Sicherheit"
Wenn Sie einen bestimmten typanbieterassembly zum ersten Mal verwenden, zeigt Visual Studio ein Dialogfeld "Sicherheit", die darauf hinweist, dass der Typanbieter ausgeführt. Bevor Sie den Typanbieter in Visual Studio geladen wird, bietet Ihnen die Gelegenheit, entscheiden, ob Sie diesen bestimmten Anbieter als vertrauenswürdig einstufen. Wenn Sie die Quelle des typanbieters vertrauen, wählen Sie "Ich vertrauen dieser Typanbieter." Wenn Sie nicht die Quelle des typanbieters vertrauen, wählen Sie "Ich vertrauen nicht dieser Typanbieter." Vertrauen den Anbieter kann innerhalb von Visual Studio ausgeführt und IntelliSense zur Verfügung stellen und Funktionen erstellen. Aber wenn Sie der Typanbieter selbst bösartig ist, Ausführen des Codes gefährden kann Ihrem Computer.

Wenn Ihr Projekt Code, der Typanbieter, die Sie im Dialogfeld ausgewählt haben enthält verweist, nicht zu vertrauen, klicken Sie dann meldet zum Zeitpunkt der Kompilierung der Compiler einen Fehler, der angibt, dass der Typanbieter nicht vertrauenswürdig ist. Alle Typen, die den nicht vertrauenswürdigen Typanbieter abhängig sind, werden durch rote Wellenlinien angezeigt. Sie können ruhig auf den Code im Editor durchsuchen.

Wenn Sie die vertrauenseinstellung direkt in Visual Studio ändern möchten, führen Sie die folgenden Schritte aus.


#### <a name="to-change-the-trust-settings-for-type-providers"></a>So ändern Sie die vertrauenseinstellungen für Typanbieter

1. Auf der `Tools` klicken Sie im Menü `Options`, und erweitern Sie die `F# Tools` Knoten.
<br />

2. Wählen Sie `Type Providers`, und klicken Sie in der Liste der Typanbieter, aktivieren Sie das Kontrollkästchen für Typanbieter, die Sie als vertrauenswürdig einstufen, und deaktivieren Sie das Kontrollkästchen für die Sie nicht vertrauen.
<br />


## <a name="see-also"></a>Siehe auch
[Typanbieter](index.md)
