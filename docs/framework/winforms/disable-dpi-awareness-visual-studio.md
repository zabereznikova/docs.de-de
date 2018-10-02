---
title: Deaktivieren Sie die DPI--Unterstützung in Visual Studio
description: Beschreibt die Einschränkungen von Windows Forms-Designer auf HDPI-Bildschirmen und wie Sie Visual Studio als DPI-Wert ohne-Prozess ausgeführt.
ms.date: 08/14/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
author: gewarren
ms.author: gewarren
ms.openlocfilehash: 7ecffedbe536f293945227d817e507f012816737
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48037040"
---
# <a name="disable-dpi-awareness-in-visual-studio"></a>Deaktivieren Sie die DPI--Unterstützung in Visual Studio

Visual Studio ist eine Punkte pro Zoll (DPI) Anwendung, die erkennt automatisch in die Anzeige Skalierungen also. Wenn eine Anwendung gibt an, dass es nicht DPI-bewusst ist, wird das Betriebssystem die Anwendung als Bitmap skaliert. Dieses Verhalten wird auch DPI-Virtualisierung bezeichnet. Die Anwendung geht immer noch, dass er auf 100 % zu skalieren oder 96 dpi ausgeführt wird.

## <a name="windows-forms-designer-on-hdpi-monitors"></a>Windows Forms-Designer auf die HDPI-Monitore

Die **Windows Forms-Designer** in Visual Studio verfügt nicht über Unterstützung für die Skalierung. Dies bewirkt, dass Probleme bei der Anzeige beim Öffnen von einige Forms in der **Windows Forms-Designer** auf hohe Punkte pro Zoll (HDPI) überwacht. Beispiele können Steuerelemente überlappen, wie in der folgenden Abbildung dargestellt angezeigt:

![Windows Forms-Designer auf HDPI-monitor](media/disable-dpi-awareness-visual-studio/win-forms-designer-hdpi.png)

In Visual Studio 2017 Version 15,8 und höher, wenn Sie einem Formular im öffnen die **Windows Forms-Designer** einen Monitor HDPI Visual Studio ein gelber Balken nur zu Informationszwecken am oberen Rand der Designer zeigt:

![Informationsleiste in Visual Studio neu starten, DPI-Wert ohne Modus](media/disable-dpi-awareness-visual-studio/scaling-gold-bar.png)

Die Nachricht liest **Skalierung auf Ihre Hauptanzeige auf 200 % (192 dpi) festgelegt ist. Dies kann dazu führen, dass Renderingprobleme im Fenster Designers.**

Wenn Sie im Designer funktionieren nicht und nicht das Layout Ihres Formulars anpassen müssen, können Sie ignorieren die Informationsleiste und weiter ausgeführt, im Code-Editor oder in anderen Typen von Designern. Nur die **Windows Forms-Designer** betroffen ist. Wenn Sie in der Sie arbeiten benötigen die **Windows Forms-Designer**, im nächste Abschnitt hilft Ihnen [lösen des Problems](#to-resolve-the-problem).

## <a name="to-resolve-the-problem"></a>Zum Beheben des Problems

Es gibt drei Möglichkeiten zum Beheben des Problems angezeigt.

### <a name="restart-visual-studio-as-a-dpi-unaware-process"></a>Starten Sie Visual Studio neu, als DPI-Wert ohne-Prozess

Sie können Visual Studio als DPI-Wert ohne Prozess neu starten, durch Auswahl der Option für die gelbe Leiste für die nur zu Informationszwecken. Dies ist die bevorzugte Methode der Behebung des Problems.

Wenn Visual Studio als DPI-Wert ohne-Prozess ausgeführt wird, wird das Designerlayout behoben wurden, aber Schriftarten werden möglicherweise unscharf angezeigt. Wenn sie als DPI-Wert ohne-Prozess ausgeführt wird, die besagt, zeigt Visual Studio einen anderen gelben informationsmeldung **Visual Studio als DPI-Wert ohne-Prozess ausgeführt wird. WPF und XAML-Designer möglicherweise nicht richtig angezeigt.** Die Informationsleiste bietet auch eine Option zum **starten Sie Visual Studio als DPI-bewusst Prozess**.

> [!NOTE]
> - Wenn Sie bei der Auswahl der Option als DPI-Wert ohne Prozess neu starten Toolfenster in Visual Studio abgedockt hatten, kann die Position des diese Toolfenster ändern.
> - Wenn Sie das Standardprofil für die Visual Basic verwenden, oder Sie haben die **neue Projekte beim Erstellen speichern** Option deaktiviert, **Tools** > **Optionen**  >  **Projekte und Projektmappen**, Visual Studio nicht wieder Ihrem Projekt öffnen, wenn es als DPI-Wert ohne Prozess neu gestartet wird. Allerdings können Sie das Projekt öffnen, wählen sie unter **Datei** > **zuletzt geöffnete Projekte und Projektmappen**.

Es ist wichtig, wenn Sie die Arbeit in fertig sind, starten Sie Visual Studio als DPI-bewusst Prozess die **Windows Forms-Designer**. Wenn es als DPI-Wert ohne-Prozess ausgeführt wird, Schriftarten können unscharf Aussehen und möglicherweise andere Designer Probleme wie z. B. die **XAML-Designer**. Wenn Sie schließen und öffnen Visual Studio aus, wenn sie in der DPI-Wert ohne Modus ausgeführt wird, steigt die DPI-bewusst erneut aus. Sie können auch klicken die **starten Sie Visual Studio als DPI-bewusst Prozess** -Option in der Informationsleiste.

### <a name="add-a-registry-entry"></a>Fügen Sie einen Registrierungseintrag hinzu.

Sie können Visual Studio als DPI-Wert ohne markieren, durch Ändern der Registrierung. Open **Registrierungs-Editor** und einen Eintrag hinzufügen die **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers** Unterschlüssel:

**Eintrag**: % ProgramFiles% (x86) %\Microsoft Visual Studio\2017\Community\Common7\IDE\devenv.exe

   > [!NOTE]
   > Wenn Sie die Professional bzw. Enterprise Edition von Visual Studio 2017 verwenden, ersetzen Sie **Community** mit **Professional** oder **Enterprise** im Eintrag.

**Typ**: REG_SZ

**Wert**: DPIUNAWARE

> [!NOTE]
> Visual Studio verbleibt im DPI-Wert ohne Modus, bis Sie den Registrierungseintrag entfernen.

### <a name="set-your-display-scaling-setting-to-100"></a>Stellen Sie die Anzeige, Skalieren die Einstellung auf 100 %

Geben Sie zum Festlegen Ihrer Anzeige, die Einstellung auf 100 % für das Skalieren von Daten in Windows 10 **Anzeigeeinstellungen** in der Taskleiste im Suchfeld ein, und wählen Sie dann **Ändern der Anzeigeeinstellungen für**. In der **Einstellungen** legen **Ändern der Größe von Text, apps und anderen Elementen** zu **100 %**.

Festlegen Ihrer Anzeige, die Skalierung auf 100 % nicht erwünscht ist, möglicherweise die Benutzeroberfläche zu klein, um verwendbar vereinfachen können.

## <a name="see-also"></a>Siehe auch

- [Automatische Skalierung in Windows Forms](automatic-scaling-in-windows-forms.md)