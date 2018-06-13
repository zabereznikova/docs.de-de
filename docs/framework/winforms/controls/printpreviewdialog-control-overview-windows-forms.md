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
ms.openlocfilehash: 0946220017fb78775f045bb225d84ea95aecd06b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538336"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="90a24-102">Übersicht über das PrintPreviewDialog-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="90a24-102">PrintPreviewDialog control overview (Windows Forms)</span></span>
<span data-ttu-id="90a24-103">Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement ist ein vorkonfiguriertes Dialogfeld zum Anzeigen verwendet wie eine [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) gedruckt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="90a24-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="90a24-104">Verwenden Sie es in Ihrer Windows-basierten Anwendung als einfache Lösung, anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="90a24-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="90a24-105">Das Steuerelement enthält Schaltflächen zum Drucken, Vergrößern, Anzeigen mindestens einer Seite und Schließen des Dialogfelds.</span><span class="sxs-lookup"><span data-stu-id="90a24-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="90a24-106">Wichtige Eigenschaften und Methoden</span><span class="sxs-lookup"><span data-stu-id="90a24-106">Key properties and methods</span></span>  
 <span data-ttu-id="90a24-107">Das Steuerelement Schlüsseleigenschaft ist <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, wodurch das Dokument in der Vorschau angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="90a24-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="90a24-108">Das Dokument muss ein <xref:System.Drawing.Printing.PrintDocument> Objekt.</span><span class="sxs-lookup"><span data-stu-id="90a24-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="90a24-109">Um das Dialogfeld anzuzeigen, rufen Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="90a24-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="90a24-110">Anti-Aliasing kann den Text glattere angezeigt, aber es kann auch die Anzeige langsamer, Legen Sie zur Verwendung der <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="90a24-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="90a24-111">Bestimmte Eigenschaften stehen über die <xref:System.Windows.Forms.PrintPreviewControl> , die die <xref:System.Windows.Forms.PrintPreviewDialog> enthält.</span><span class="sxs-lookup"><span data-stu-id="90a24-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="90a24-112">(Sie müssen nicht dies hinzufügen <xref:System.Windows.Forms.PrintPreviewControl> in das Formular; er ist automatisch enthalten, innerhalb der <xref:System.Windows.Forms.PrintPreviewDialog> Wenn Sie das Dialogfeld zum Formular hinzufügen.) Beispiele für Eigenschaften, die über die <xref:System.Windows.Forms.PrintPreviewControl> sind die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> und <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> Eigenschaften, die bestimmen, die Anzahl der Seiten, die horizontal und vertikal auf dem Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="90a24-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="90a24-113">Sie können den Zugriff auf die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> Eigenschaft als `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#- oder `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90a24-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span></span>  
  
## <a name="printpreviewdialog-performance"></a><span data-ttu-id="90a24-114">PrintPreviewDialog-Leistung</span><span class="sxs-lookup"><span data-stu-id="90a24-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="90a24-115">Unter den folgenden Bedingungen die <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement sehr langsam initialisiert:</span><span class="sxs-lookup"><span data-stu-id="90a24-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="90a24-116">Ein Netzwerkdrucker wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="90a24-116">A network printer is used.</span></span>
- <span data-ttu-id="90a24-117">Benutzereinstellungen für diesen Drucker, wie z. B. duplex Einstellungen werden geändert.</span><span class="sxs-lookup"><span data-stu-id="90a24-117">User preferences for this printer, such as duplex settings, are modified.</span></span>
  
<span data-ttu-id="90a24-118">Für apps, die auf .NET Framework 4.5.2 ausgeführt werden, können Sie den folgenden Schlüssel zum Hinzufügen der \<"appSettings" > Abschnitt der Konfigurationsdatei zum Verbessern der Leistung von <xref:System.Windows.Forms.PrintPreviewDialog> Initialisierung zu steuern:</span><span class="sxs-lookup"><span data-stu-id="90a24-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
<span data-ttu-id="90a24-119">Wenn die `EnablePrintPreviewOptimization` Schlüssel in einen anderen Wert festgelegt ist, oder wenn der Schlüssel nicht vorhanden ist, wird die Optimierung wird nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="90a24-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="90a24-120">Für apps, die auf .NET Framework 4.6 oder höher ausgeführt werden, können Sie die folgenden Schalter zum Hinzufügen der [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) Element in der [ \<Runtime >](../../configure-apps/file-schema/runtime/index.md) die Datei "App.config" im Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="90a24-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
<span data-ttu-id="90a24-121">Wenn der Schalter nicht vorhanden ist oder wenn sie einen anderen Wert festgelegt ist, wird die Optimierung nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="90a24-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span> 

<span data-ttu-id="90a24-122">Bei Verwendung der <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> Ereignis zum Ändern von Druckereinstellungen fest, die Leistung der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement wird nicht verbessert werden, auch wenn eine Optimierung Konfigurationsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="90a24-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>  

## <a name="see-also"></a><span data-ttu-id="90a24-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90a24-123">See also</span></span>  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [<span data-ttu-id="90a24-124">Übersicht über das PrintPreviewControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="90a24-124">PrintPreviewControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="90a24-125">PrintPreviewDialog-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="90a24-125">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="90a24-126">Dialogfeld-Steuerelemente und -Komponenten</span><span class="sxs-lookup"><span data-stu-id="90a24-126">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
