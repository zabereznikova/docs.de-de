---
title: Übersicht über das PrintPreviewDialog-Steuerelement
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
ms.openlocfilehash: 6fb971493336cda1e04c720dd09147e650918c3a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741408"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Übersicht über das PrintPreviewDialog-Steuerelement (Windows Forms)

Das Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement ist ein vorkonfiguriertes Dialogfeld, in dem angezeigt wird, wie ein [PrintDocument](printdocument-component-windows-forms.md) angezeigt wird, wenn es gedruckt wird. Verwenden Sie es in Ihrer Windows-basierten Anwendung als einfache Lösung, anstatt ein eigenes Dialogfeld zu konfigurieren. Das Steuerelement enthält Schaltflächen zum Drucken, Vergrößern, Anzeigen mindestens einer Seite und Schließen des Dialogfelds.

## <a name="key-properties-and-methods"></a>Schlüsseleigenschaften und-Methoden

Die Schlüsseleigenschaft des Steuer Elements ist <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, wodurch das Dokument als Vorschau angezeigt wird. Das Dokument muss ein <xref:System.Drawing.Printing.PrintDocument> Objekt sein. Um das Dialogfeld anzuzeigen, müssen Sie dessen <xref:System.Windows.Forms.Form.ShowDialog%2A>-Methode aufrufen. Antialiasing kann dazu führen, dass der Text glatter erscheint, aber auch die Anzeige langsamer wird. Legen Sie die <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A>-Eigenschaft auf `true`fest, um Sie zu verwenden.

Bestimmte Eigenschaften sind über die <xref:System.Windows.Forms.PrintPreviewControl> verfügbar, die die <xref:System.Windows.Forms.PrintPreviewDialog> enthält. (Sie müssen diese <xref:System.Windows.Forms.PrintPreviewControl> dem Formular nicht hinzufügen. Sie ist automatisch im <xref:System.Windows.Forms.PrintPreviewDialog> enthalten, wenn Sie das Dialogfeld zum Formular hinzufügen.) Beispiele für Eigenschaften, die über die <xref:System.Windows.Forms.PrintPreviewControl> verfügbar sind, sind die Eigenschaften <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> und <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>, die bestimmen, wie viele Seiten horizontal und vertikal auf dem Steuerelement angezeigt werden. Sie können auf die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>-Eigenschaft als `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in C#Visual oder `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++zugreifen.

## <a name="printpreviewdialog-performance"></a>PrintPreviewDialog-Leistung

Unter den folgenden Bedingungen wird das <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement sehr langsam initialisiert:

- Ein Netzwerkdrucker wird verwendet.
- Die Benutzereinstellungen für diesen Drucker (z. b. Duplex Einstellungen) werden geändert.

Für apps, die auf dem .NET Framework 4.5.2 ausgeführt werden, können Sie den folgenden Schlüssel zum \<appSettings-> Abschnitt der Konfigurationsdatei hinzufügen, um die Leistung der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerungs Initialisierung zu verbessern:

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

Wenn der `EnablePrintPreviewOptimization` Schlüssel auf einen anderen Wert festgelegt ist, oder wenn der Schlüssel nicht vorhanden ist, wird die Optimierung nicht angewendet.

Für apps, die unter .NET Framework 4,6 oder höheren Versionen ausgeführt werden, können Sie den folgenden Schalter dem [\<appcontexungwitchoverrides->](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) -Element im [\<Runtime->](../../configure-apps/file-schema/runtime/index.md) Abschnitt der APP-Konfigurationsdatei hinzufügen:

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

Wenn der Schalter nicht vorhanden ist oder auf einen anderen Wert festgelegt ist, wird die Optimierung nicht angewendet.

Wenn Sie das <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings>-Ereignis verwenden, um Druckereinstellungen zu ändern, wird die Leistung des <xref:System.Windows.Forms.PrintPreviewDialog> Steuer Elements nicht verbessert, auch wenn ein Optimierungs Konfigurationsschalter festgelegt ist.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [Übersicht über das PrintPreviewControl-Steuerelement](printpreviewcontrol-control-overview-windows-forms.md)
- [PrintPreviewDialog-Steuerelement](printpreviewdialog-control-windows-forms.md)
- [Dialogfeld-Steuerelemente und -Komponenten](dialog-box-controls-and-components-windows-forms.md)
