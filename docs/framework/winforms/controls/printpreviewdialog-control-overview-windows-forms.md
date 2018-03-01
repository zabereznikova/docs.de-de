---
title: "Übersicht über das PrintPreviewDialog-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 01/08/2018
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1228a3cf39ea412cde341c4c4b8b83e0ab2f0299
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2018
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Übersicht über das PrintPreviewDialog-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement ist ein vorkonfiguriertes Dialogfeld zum Anzeigen verwendet wie eine [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) gedruckt wird angezeigt. Verwenden Sie es in Ihrer Windows-basierten Anwendung als einfache Lösung, anstatt ein eigenes Dialogfeld zu konfigurieren. Das Steuerelement enthält Schaltflächen zum Drucken, Vergrößern, Anzeigen mindestens einer Seite und Schließen des Dialogfelds.  
  
## <a name="key-properties-and-methods"></a>Wichtige Eigenschaften und Methoden  
 Das Steuerelement Schlüsseleigenschaft ist <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, wodurch das Dokument in der Vorschau angezeigt werden. Das Dokument muss ein <xref:System.Drawing.Printing.PrintDocument> Objekt. Um das Dialogfeld anzuzeigen, rufen Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A> Methode. Anti-Aliasing kann den Text glattere angezeigt, aber es kann auch die Anzeige langsamer, Legen Sie zur Verwendung der <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> Eigenschaft `true`.  
  
 Bestimmte Eigenschaften stehen über die <xref:System.Windows.Forms.PrintPreviewControl> , die die <xref:System.Windows.Forms.PrintPreviewDialog> enthält. (Sie müssen nicht dies hinzufügen <xref:System.Windows.Forms.PrintPreviewControl> in das Formular; er ist automatisch enthalten, innerhalb der <xref:System.Windows.Forms.PrintPreviewDialog> Wenn Sie das Dialogfeld zum Formular hinzufügen.) Beispiele für Eigenschaften, die über die <xref:System.Windows.Forms.PrintPreviewControl> sind die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> und <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> Eigenschaften, die bestimmen, die Anzahl der Seiten, die horizontal und vertikal auf dem Steuerelement angezeigt. Sie können den Zugriff auf die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> Eigenschaft als `PrintPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], oder `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].  
  
## <a name="printpreviewdialog-performance"></a>PrintPreviewDialog-Leistung

Unter den folgenden Bedingungen die <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement sehr langsam initialisiert:

- Ein Netzwerkdrucker wird verwendet.
- Benutzereinstellungen für diesen Drucker, wie z. B. duplex Einstellungen werden geändert.
  
Für apps, die auf .NET Framework 4.5.2 ausgeführt werden, können Sie den folgenden Schlüssel zum Hinzufügen der \<"appSettings" > Abschnitt der Konfigurationsdatei zum Verbessern der Leistung von <xref:System.Windows.Forms.PrintPreviewDialog> Initialisierung zu steuern:

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
Wenn die `EnablePrintPreviewOptimization` Schlüssel in einen anderen Wert festgelegt ist, oder wenn der Schlüssel nicht vorhanden ist, wird die Optimierung wird nicht angewendet.

Für apps, die auf .NET Framework 4.6 oder höher ausgeführt werden, können Sie die folgenden Schalter zum Hinzufügen der [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) Element in der [ \<Runtime >](../../configure-apps/file-schema/runtime/index.md) die Datei "App.config" im Abschnitt:

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
Wenn der Schalter nicht vorhanden ist oder wenn sie einen anderen Wert festgelegt ist, wird die Optimierung nicht angewendet. 

Bei Verwendung der <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> Ereignis zum Ändern von Druckereinstellungen fest, die Leistung der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement wird nicht verbessert werden, auch wenn eine Optimierung Konfigurationsschalter festgelegt ist.  

## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [Übersicht über das PrintPreviewControl-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [PrintPreviewDialog-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [Dialogfeld-Steuerelemente und -Komponenten](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
