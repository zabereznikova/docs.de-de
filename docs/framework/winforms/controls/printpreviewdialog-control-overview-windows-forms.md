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
ms.openlocfilehash: aad8673051b22db1df6d525094394dd2a43285ca
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711277"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="985db-102">Übersicht über das PrintPreviewDialog-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="985db-102">PrintPreviewDialog control overview (Windows Forms)</span></span>
<span data-ttu-id="985db-103">Die Windows-Formulare <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement ist ein vorkonfiguriertes Dialogfeld zum Anzeigen verwendet wie ein [PrintDocument](printdocument-component-windows-forms.md) wird angezeigt, gedruckt.</span><span class="sxs-lookup"><span data-stu-id="985db-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="985db-104">Verwenden Sie es in Ihrer Windows-basierte Anwendung als einfache Lösung anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="985db-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="985db-105">Das Steuerelement enthält Schaltflächen zum Drucken, Vergrößern, Anzeigen mindestens einer Seite und Schließen des Dialogfelds.</span><span class="sxs-lookup"><span data-stu-id="985db-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="985db-106">Wichtige Eigenschaften und Methoden</span><span class="sxs-lookup"><span data-stu-id="985db-106">Key properties and methods</span></span>  
 <span data-ttu-id="985db-107">Die Schlüsseleigenschaft des Steuerelements ist <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, wodurch das Dokument, in der Vorschau angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="985db-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="985db-108">Das Dokument muss ein <xref:System.Drawing.Printing.PrintDocument> Objekt.</span><span class="sxs-lookup"><span data-stu-id="985db-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="985db-109">Um das Dialogfeld anzuzeigen, rufen Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="985db-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="985db-110">Anti-Aliasing kann legen Sie den Text, der reibungslose angezeigt werden kann, jedoch auch die Anzeige langsamer; um es zu verwenden, legen die <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="985db-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="985db-111">Bestimmte Eigenschaften stehen über die <xref:System.Windows.Forms.PrintPreviewControl> , die die <xref:System.Windows.Forms.PrintPreviewDialog> enthält.</span><span class="sxs-lookup"><span data-stu-id="985db-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="985db-112">(Sie müssen keine Hiermit <xref:System.Windows.Forms.PrintPreviewControl> dem Formular wird es automatisch in enthalten die <xref:System.Windows.Forms.PrintPreviewDialog> Wenn Sie das Dialogfeld zum Formular hinzufügen.) Beispiele für Eigenschaften, die über die <xref:System.Windows.Forms.PrintPreviewControl> sind die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> und <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> Eigenschaften, die bestimmen, die Anzahl der Seiten, die horizontal und vertikal auf dem Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="985db-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="985db-113">Sie erreichen die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> Eigenschaft als `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic `printPreviewDialog1.PrintPreviewControl.Columns` in visuellen C#, oder `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span><span class="sxs-lookup"><span data-stu-id="985db-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].</span></span>  
  
## <a name="printpreviewdialog-performance"></a><span data-ttu-id="985db-114">PrintPreviewDialog-Leistung</span><span class="sxs-lookup"><span data-stu-id="985db-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="985db-115">Unter den folgenden Bedingungen die <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement nur sehr langsam initialisiert:</span><span class="sxs-lookup"><span data-stu-id="985db-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="985db-116">Wird verwendet, ein Netzwerkdrucker.</span><span class="sxs-lookup"><span data-stu-id="985db-116">A network printer is used.</span></span>
- <span data-ttu-id="985db-117">Benutzereinstellungen für diesen Drucker, z. B. duplex-Einstellungen werden geändert.</span><span class="sxs-lookup"><span data-stu-id="985db-117">User preferences for this printer, such as duplex settings, are modified.</span></span>
  
<span data-ttu-id="985db-118">Für apps, die auf .NET Framework 4.5.2 ausgeführt werden, können Sie den folgenden Schlüssel zum Hinzufügen der \<AppSettings > Abschnitt der Konfigurationsdatei zur Verbesserung der Leistung von <xref:System.Windows.Forms.PrintPreviewDialog> Initialisierung zu steuern:</span><span class="sxs-lookup"><span data-stu-id="985db-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```
<span data-ttu-id="985db-119">Wenn die `EnablePrintPreviewOptimization` Schlüssel auf einen anderen Wert festgelegt ist, oder wenn der Schlüssel nicht vorhanden ist, wird die Optimierung wird nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="985db-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="985db-120">Für apps, die auf die .NET Framework 4.6 oder höher ausgeführt wird, können Sie die folgende Option zum Hinzufügen der [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) Element in der [ \<Runtime >](../../configure-apps/file-schema/runtime/index.md) im Abschnitt Ihrer Datei "App.config":</span><span class="sxs-lookup"><span data-stu-id="985db-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
``` 
<span data-ttu-id="985db-121">Wenn der Switch nicht vorhanden ist, oder wenn sie auf einen anderen Wert festgelegt ist, wird die Optimierung nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="985db-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span> 

<span data-ttu-id="985db-122">Bei Verwendung der <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> Ereignis zum Ändern von Druckereinstellungen fest, die Leistung der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement wird nicht verbessert werden, auch wenn eine Optimierung Konfigurationsschalters festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="985db-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>  

## <a name="see-also"></a><span data-ttu-id="985db-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="985db-123">See also</span></span>
- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="985db-124">Übersicht über das PrintPreviewControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="985db-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="985db-125">PrintPreviewDialog-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="985db-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="985db-126">Dialogfeld-Steuerelemente und -Komponenten</span><span class="sxs-lookup"><span data-stu-id="985db-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
