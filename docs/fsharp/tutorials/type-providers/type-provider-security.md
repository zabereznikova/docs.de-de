---
title: Sicherheit von Typanbietern
description: Erfahren Sie mehr über die Sicherheit von typanbietern in F#, wie Sie die Einstellungen für einen Typanbieter für die Vertrauensstellung zu ändern.
ms.date: 05/16/2016
ms.openlocfilehash: 9ccb33d7298736c3d6b54980b6fe09bc9f2e0259
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611190"
---
# <a name="type-provider-security"></a>Sicherheit von Typanbietern

Typanbieter sind Assemblys (DLLs) durch Ihre F#-Projekt oder das Skript verwiesen wird, die Code enthalten, um eine Verbindung mit externen Datenquellen herstellen und diese Typinformationen in der F#-Typ-Umgebung auftreten. In der Regel wird Code in referenzierten Assemblys nur ausgeführt, beim Kompilieren, und klicken Sie dann den Code ausführen (oder bei einem Skript den Code an F# Interactive senden). Eine typanbieterassembly wird jedoch innerhalb von Visual Studio ausgeführt werden, wenn lediglich der Code im Editor durchsucht wird. Dies geschieht, weil der Typanbieter müssen ausführen, um zusätzliche Informationen in den Editor, z. B. QuickInfos, IntelliSense-Vervollständigung, hinzufügen und so weiter. Daher sind gibt es zusätzliche sicherheitsüberlegungen für den Typ Anbieterassemblys, da sie automatisch in Visual Studio-Prozesses ausgeführt.

## <a name="security-warning-dialog"></a>Sicherheitswarnungs-Dialogfeld

Wenn Sie eine bestimmten typanbieterassembly zum ersten Mal verwenden, zeigt Visual Studio ein Sicherheitsdialogfeld an, die darauf hinweist, dass der Typanbieter wird gleich ausgeführt. Bevor Sie den Typanbieter in Visual Studio geladen wird, erhalten Sie die Möglichkeit zu entscheiden, ob Sie diesen bestimmten Anbieter als vertrauenswürdig einstufen. Wenn Sie die Quelle des typanbieters vertrauen, wählen Sie dann "Ich vertraue dieser Typanbieter." Wenn Sie nicht über die Quelle des typanbieters vertrauen, wählen Sie "Ich nicht diesem Anbieter vertrauen." Vertrauen den Anbieter ermöglicht, führen Sie in Visual Studio und IntelliSense-Funktionalität bereitstellen und die Funktionen erstellen. Aber wenn Sie der Typanbieter selbst bösartig ist, Ausführen des Codes gefährden kann Ihrem Computer.

Wenn Ihr Projekt Code, der Typanbieter, die Sie im Dialogfeld ausgewählt haben enthält verweist, nicht zu vertrauen, klicken Sie dann meldet zum Zeitpunkt der Kompilierung der Compiler einen Fehler, der angibt, dass der Typanbieter nicht vertrauenswürdig ist. Alle Typen, die den nicht vertrauenswürdigen Typanbieter abhängig sind, werden durch rote Wellenlinien angezeigt. Es ist sicher, um den Code im Editor zu durchsuchen.

Wenn Sie die vertrauenseinstellung direkt in Visual Studio ändern möchten, führen Sie die folgenden Schritte aus.

### <a name="to-change-the-trust-settings-for-type-providers"></a>So ändern Sie die Einstellungen für die Vertrauensstellung für Typanbieter

1. Auf der `Tools` , wählen Sie im Menü `Options`, und erweitern Sie die `F# Tools` Knoten.

2. Wählen Sie `Type Providers`, und klicken Sie in der Liste der Typanbieter, aktivieren Sie das Kontrollkästchen für Typanbieter, der Sie vertrauen, und deaktivieren Sie das Kontrollkästchen für die Sie nicht vertrauen.

## <a name="see-also"></a>Siehe auch

- [Typanbieter](index.md)