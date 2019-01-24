---
title: Übersicht über das PrintPreviewDialog-Steuerelement (Windows Forms)
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e28a6c82a8dd40885c04c56f2adfb3d38e674066
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667556"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Übersicht über das PrintPreviewDialog-Steuerelement (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement ist ein vorkonfiguriertes Dialogfeld zum Anzeigen verwendet wie ein [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) wird angezeigt, gedruckt. Verwenden Sie es in Ihrer Windows-basierte Anwendung als einfache Lösung anstatt ein eigenes Dialogfeld zu konfigurieren. Das Steuerelement enthält Schaltflächen zum Drucken, Vergrößern, Anzeigen mindestens einer Seite und Schließen des Dialogfelds.  
  
## <a name="key-properties-and-methods"></a>Wichtige Eigenschaften und Methoden  
 Die Schlüsseleigenschaft des Steuerelements ist <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, wodurch das Dokument, in der Vorschau angezeigt werden. Das Dokument muss ein <xref:System.Drawing.Printing.PrintDocument> Objekt. Um das Dialogfeld anzuzeigen, rufen Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A> Methode. Anti-Aliasing kann legen Sie den Text, der reibungslose angezeigt werden kann, jedoch auch die Anzeige langsamer; um es zu verwenden, legen die <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> Eigenschaft `true`.  
  
 Bestimmte Eigenschaften stehen über die <xref:System.Windows.Forms.PrintPreviewControl> , die die <xref:System.Windows.Forms.PrintPreviewDialog> enthält. (Sie müssen keine Hiermit <xref:System.Windows.Forms.PrintPreviewControl> dem Formular wird es automatisch in enthalten die <xref:System.Windows.Forms.PrintPreviewDialog> Wenn Sie das Dialogfeld zum Formular hinzufügen.) Beispiele für Eigenschaften, die über die <xref:System.Windows.Forms.PrintPreviewControl> sind die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> und <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> Eigenschaften, die bestimmen, die Anzahl der Seiten, die horizontal und vertikal auf dem Steuerelement angezeigt. Sie erreichen die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> Eigenschaft als `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic `printPreviewDialog1.PrintPreviewControl.Columns` in visuellen C#, oder `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].  
  
## <a name="printpreviewdialog-performance"></a>PrintPreviewDialog-Leistung

Unter den folgenden Bedingungen die <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement nur sehr langsam initialisiert:

- Wird verwendet, ein Netzwerkdrucker.
- Benutzereinstellungen für diesen Drucker, z. B. duplex-Einstellungen werden geändert.
  
Für apps, die auf .NET Framework 4.5.2 ausgeführt werden, können Sie den folgenden Schlüssel zum Hinzufügen der \<AppSettings > Abschnitt der Konfigurationsdatei zur Verbesserung der Leistung von <xref:System.Windows.Forms.PrintPreviewDialog> Initialisierung zu steuern:

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
Wenn die `EnablePrintPreviewOptimization` Schlüssel auf einen anderen Wert festgelegt ist, oder wenn der Schlüssel nicht vorhanden ist, wird die Optimierung wird nicht angewendet.

Für apps, die auf die .NET Framework 4.6 oder höher ausgeführt wird, können Sie die folgende Option zum Hinzufügen der [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) Element in der [ \<Runtime >](../../configure-apps/file-schema/runtime/index.md) im Abschnitt Ihrer Datei "App.config":

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
Wenn der Switch nicht vorhanden ist, oder wenn sie auf einen anderen Wert festgelegt ist, wird die Optimierung nicht angewendet. 

Bei Verwendung der <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> Ereignis zum Ändern von Druckereinstellungen fest, die Leistung der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement wird nicht verbessert werden, auch wenn eine Optimierung Konfigurationsschalters festgelegt ist.  

## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.PrintPreviewDialog>
- [Übersicht über das PrintPreviewControl-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)
- [PrintPreviewDialog-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)
- [Dialogfeld-Steuerelemente und -Komponenten](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
