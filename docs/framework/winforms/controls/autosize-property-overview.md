---
title: Übersicht über die AutoSize-Eigenschaft
ms.date: 03/30/2017
helpviewer_keywords:
- sizing [Windows Forms], automatic
- layout [Windows Forms], AutoSize
- automatic sizing
- AutoSizeMode property
ms.assetid: 62fd82a2-9565-4f65-925b-9d1e66dc4e7d
ms.openlocfilehash: 6d5c4a22f186ddc5811c4a4d5e79776decea9e50
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173627"
---
# <a name="autosize-property-overview"></a>Übersicht über die AutoSize-Eigenschaft
Die <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft mit der ein Steuerelement so ändern Sie die Größe bei Bedarf, um den vom angegebenen Wert erreicht die <xref:System.Windows.Forms.Control.PreferredSize%2A> Eigenschaft. Sie stellen das Größenanpassungsverhalten für bestimmte Steuerelemente, durch Festlegen der `AutoSizeMode` Eigenschaft.  
  
## <a name="autosize-behavior"></a>Das AutoSize-Verhalten  
 Nur einige Steuerelemente unterstützen das <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft. Darüber hinaus unterstützen einige Steuerelemente, die <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft unterstützen auch die `AutoSizeMode` Eigenschaft.  
  
 Die <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft erzeugt ein geringfügig anderes Verhalten, je nach den bestimmten Steuerelementtyp und den Wert des der `AutoSizeMode` -Eigenschaft, wenn die Eigenschaft vorhanden ist. In der folgende Tabelle wird beschrieben, die Verhaltensweisen, die immer "true" sind, und enthält eine kurze Beschreibung der einzelnen:  
  
|Immer "true" Verhalten|Beschreibung|  
|--------------------------|-----------------|  
|Automatische größenanpassung ist eine Run-Time-Funktion.|Dies bedeutet, dass es nie vergrößert oder verkleinert wird ein Steuerelement und dann hat keine weitere Auswirkung.|  
|Wenn die Größe, den Wert eines Steuerelements ändert seine <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft bleibt immer konstant.|Wenn der Inhalt des Steuerelements vergrößert verursachen, wächst das Steuerelement, an der rechten Seite und nach unten. Steuerelemente vergrößern auf der linken Seite nicht.|  
|Die <xref:System.Windows.Forms.Control.Dock%2A> und <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaften werden berücksichtigt, wenn <xref:System.Windows.Forms.Control.AutoSize%2A> ist `true`.|Der Wert des Steuerelements <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft wird auf den richtigen Wert angepasst.<br /><br /> **Beachten Sie** der <xref:System.Windows.Forms.Label> -Steuerelement stellt die Ausnahme von dieser Regel. Beim Festlegen des Wert eines angedockten <xref:System.Windows.Forms.Label> des Steuerelements <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft `true`, <xref:System.Windows.Forms.Label> -Steuerelement nicht gestreckt.|  
|Eines Steuerelements <xref:System.Windows.Forms.Control.MaximumSize%2A> und <xref:System.Windows.Forms.Control.MinimumSize%2A> Eigenschaften immer beachtet, unabhängig vom Wert für die <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft.|Die <xref:System.Windows.Forms.Control.MaximumSize%2A> und <xref:System.Windows.Forms.Control.MinimumSize%2A> Eigenschaften sind nicht betroffen, durch die <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft.|  
|Es ist keine minimale Größe, die standardmäßig festgelegt.|Dies bedeutet, dass ein Steuerelement festgelegt ist, unter Verkleinern <xref:System.Windows.Forms.Control.AutoSize%2A> und hat keinen Inhalt, den Wert des der <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft ist 0,0. In diesem Fall wird das Steuerelement zu einem Zeitpunkt verkleinert, und es wird nicht direkt sichtbar sein.|  
|Wenn ein Steuerelement nicht implementiert die <xref:System.Windows.Forms.Control.GetPreferredSize%2A> -Methode, die <xref:System.Windows.Forms.Control.GetPreferredSize%2A> Methodenrückgabe letzten zugewiesenen Wert der <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft.|Dies bedeutet, dass diese Einstellung <xref:System.Windows.Forms.Control.AutoSize%2A> zu `true` hat keine Auswirkungen.|  
|Ein Steuerelement in einem <xref:System.Windows.Forms.TableLayoutPanel> Zelle immer Verkleinerung für die Zelle erst die <xref:System.Windows.Forms.Control.MinimumSize%2A> erreicht ist.|Diese Größe wird als eine maximale Größe erzwungen. Dies ist nicht der Fall, wenn die Zelle gehört eine <xref:System.Windows.Forms.SizeType.AutoSize> Zeile oder Spalte.|  
  
## <a name="autosizemode-property"></a>AutoSizeMode-Eigenschaft  
 Die `AutoSizeMode` Eigenschaft ermöglicht eine präzisere Kontrolle über das standardmäßige <xref:System.Windows.Forms.Control.AutoSize%2A> Verhalten. Die `AutoSizeMode` Eigenschaft gibt an, wie sich die Größe ein Steuerelements an dessen Inhalt anpasst. Der Inhalt, z. B. möglicherweise den Text für ein <xref:System.Windows.Forms.Button> Steuerelement oder die untergeordneten Steuerelemente für einen Container.  
  
 Die folgende Tabelle zeigt die <xref:System.Windows.Forms.AutoSizeMode> Einstellungen und eine Beschreibung des Verhaltens jeder Einstellung werden, wird der.  
  
|AutoSizeMode-Einstellung|Verhalten|  
|--------------------------|--------------|  
|GrowAndShrink|Das Steuerelement vergrößert oder verkleinert, um seinen Inhalt umgibt.<br /><br /> Die <xref:System.Windows.Forms.Control.MinimumSize%2A> und <xref:System.Windows.Forms.Control.MaximumSize%2A> Werte berücksichtigt werden, aber der aktuelle Wert von der <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft wird ignoriert.<br /><br /> Dies ist das gleiche Verhalten wie die Steuerelemente mit den <xref:System.Windows.Forms.Control.AutoSize%2A> -Eigenschaft und kein `AutoSizeMode` Eigenschaft.|  
|GrowOnly|Das Steuerelement vergrößert wird, so weit wie erforderlich, um seinen Inhalt umfassen, aber es wird nicht kleiner als der Wert von verkleinert die <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft.<br /><br /> Dies ist der Standardwert für `AutoSizeMode`.|  
  
## <a name="controls-that-support-the-autosize-property"></a>Steuerelemente, die der AutoSize-Eigenschaft unterstützen  
 Die folgende Tabelle listet die Steuerelemente, die Unterstützung der <xref:System.Windows.Forms.Control.AutoSize%2A> und `AutoSizeMode` Eigenschaften.  
  
|AutoSize-Unterstützung|Steuerelementtyp|  
|----------------------|------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> die Eigenschaft unterstützt.<br />-Keine `AutoSizeMode` Eigenschaft.|<xref:System.Windows.Forms.CheckBox><br /><br /> <xref:System.Windows.Forms.DomainUpDown><br /><br /> <xref:System.Windows.Forms.Label><br /><br /> <xref:System.Windows.Forms.LinkLabel><br /><br /> <xref:System.Windows.Forms.MaskedTextBox> (<xref:System.Windows.Forms.TextBox> Basis)<br /><br /> <xref:System.Windows.Forms.NumericUpDown><br /><br /> <xref:System.Windows.Forms.RadioButton><br /><br /> <xref:System.Windows.Forms.TextBox><br /><br /> <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> die Eigenschaft unterstützt.<br />-   `AutoSizeMode` die Eigenschaft unterstützt.|<xref:System.Windows.Forms.Button><br /><br /> <xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.FlowLayoutPanel><br /><br /> <xref:System.Windows.Forms.Form><br /><br /> <xref:System.Windows.Forms.GroupBox><br /><br /> <xref:System.Windows.Forms.Panel><br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>|  
|-Keine <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft.|<xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.ComboBox><br /><br /> <xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DateTimePicker><br /><br /> <xref:System.Windows.Forms.ListBox><br /><br /> <xref:System.Windows.Forms.ListView><br /><br /> <xref:System.Windows.Forms.MaskedTextBox><br /><br /> <xref:System.Windows.Forms.MonthCalendar><br /><br /> <xref:System.Windows.Forms.ProgressBar><br /><br /> <xref:System.Windows.Forms.PropertyGrid><br /><br /> <xref:System.Windows.Forms.RichTextBox><br /><br /> <xref:System.Windows.Forms.SplitContainer><br /><br /> <xref:System.Windows.Forms.TabControl><br /><br /> <xref:System.Windows.Forms.TabPage><br /><br /> <xref:System.Windows.Forms.TreeView><br /><br /> <xref:System.Windows.Forms.WebBrowser><br /><br /> <xref:System.Windows.Forms.ScrollBar>|  
  
## <a name="autosize-in-the-design-environment"></a>Automatisches Anpassen der Größe in der Entwurfsumgebung  
 Die folgende Tabelle beschreibt das Größenanpassungsverhalten eines Steuerelements zur Entwurfszeit anhand des Werts, der die <xref:System.Windows.Forms.Control.AutoSize%2A> und `AutoSizeMode` Eigenschaften.  
  
 Überschreiben der <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A> Eigenschaft, um zu bestimmen, ob ein bestimmtes Steuerelement Benutzer angepasst werden kann. In der folgenden Tabelle, "kann nicht" bedeutet, dass <xref:System.Windows.Forms.Design.SelectionRules.Moveable> nur "kann" bedeutet, dass <xref:System.Windows.Forms.Design.SelectionRules.AllSizeable> und <xref:System.Windows.Forms.Design.SelectionRules.Moveable>.  
  
|AutoSize-Einstellungen|Größenanpassung des Entwurfszeit-Bewegung|  
|-----------------------|---------------------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-Keine `AutoSizeMode` Eigenschaft.|Der Benutzer kann nicht die Größe des Steuerelements zur Entwurfszeit mit Ausnahme der folgenden Steuerelemente:<br /><br /> -   <xref:System.Windows.Forms.TextBox><br />-   <xref:System.Windows.Forms.MaskedTextBox><br />-   <xref:System.Windows.Forms.RichTextBox><br />-   <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>|Der Benutzer kann nicht die Größe des Steuerelements zur Entwurfszeit.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>|Der Benutzer kann die Größe des Steuerelements zur Entwurfszeit. Wenn die <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft festgelegt ist, wird der Benutzer kann nur die Größe des Steuerelements erhöhen.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `false`, oder <xref:System.Windows.Forms.Control.AutoSize%2A> -Eigenschaft wird ausgeblendet.|Benutzer kann die Größe des Steuerelements zur Entwurfszeit.|  
  
> [!NOTE]
>  Zum Maximieren der Produktivität "," Schatten auf der Windows Forms-Designer die <xref:System.Windows.Forms.Control.AutoSize%2A> -Eigenschaft für die <xref:System.Windows.Forms.Form> Klasse. Zur Entwurfszeit verhält sich das Formular als ob die <xref:System.Windows.Forms.Control.AutoSize%2A> -Eigenschaftensatz auf `false`, unabhängig von der tatsächlichen Einstellung. Zur Laufzeit keine spezielle Einrichtung vorgenommen wird, und die <xref:System.Windows.Forms.Control.AutoSize%2A> -Eigenschaft angewendet wird gemäß der Einstellung der Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.PreferredSize%2A>
- <xref:System.Windows.Forms.Control.GetPreferredSize%2A>
