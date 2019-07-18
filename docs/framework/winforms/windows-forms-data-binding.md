---
title: Datenbindung in Web Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
ms.openlocfilehash: ed456807137e8cf7594bc50eb0eebb67b88e6b40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800112"
---
# <a name="windows-forms-data-binding"></a>Datenbindung in Web Forms
Mit der Datenbindung in Windows Forms erhalten Sie die Möglichkeit, Informationen aus einer Datenquelle in Steuerelementen im Formular anzuzeigen und zu ändern. Sie können sowohl herkömmliche Datenquellen als auch beinahe alle Strukturen binden, die Daten enthalten.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Datenbindung und Windows Forms](data-binding-and-windows-forms.md)  
 Bietet eine Übersicht über die Datenbindung in Windows Forms.  
  
 [Von Windows Forms unterstützte Datenquellen](data-sources-supported-by-windows-forms.md)  
 Beschreibt die Datenquellen, die in Verbindung mit Windows Forms verwendet werden können.  
  
 [Auf Datenbindung bezogene Schnittstellen](interfaces-related-to-data-binding.md)  
 Beschreibt einige der Schnittstellen, die für die Windows Forms-Datenbindung verwendet werden.  
  
 [Vorgehensweise: Navigieren Sie durch Daten in Windows Forms](how-to-navigate-data-in-windows-forms.md)  
 Zeigt, wie Sie in den Elementen einer Datenquelle navigieren können.  
  
 [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](change-notification-in-windows-forms-data-binding.md)  
 Beschreibt die unterschiedlichen Arten von Änderungsbenachrichtigungen für die Datenbindung in Windows Forms.  
  
 [Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle](how-to-implement-the-inotifypropertychanged-interface.md)  
 Zeigt, wie die <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle implementiert wird. Die Schnittstelle übergibt die Eigenschaftenänderungen an einem Geschäftsobjekt an ein gebundenes Steuerelement.  
  
 [Vorgehensweise: Anwenden des PropertyNameChanged-Musters](how-to-apply-the-propertynamechanged-pattern.md)  
 Veranschaulicht das Anwenden der *PropertyName*-Muster auf die Eigenschaften eines Windows Forms-Benutzersteuerelements.  
  
 [Vorgehensweise: Implementieren der ITypedList-Schnittstelle](how-to-implement-the-itypedlist-interface.md)  
 Zeigt, wie die Ermittlung des Schemas für eine bindbare Liste durch Implementieren der <xref:System.ComponentModel.ITypedList>-Schnittstelle ermöglicht wird.  
  
 [Vorgehensweise: Implementieren der IListSource-Schnittstelle](how-to-implement-the-ilistsource-interface.md)  
 Zeigt, wie die <xref:System.ComponentModel.IListSource>-Schnittstelle implementiert wird, um eine bindbare Klasse zu erstellen, die nicht <xref:System.Collections.IList> implementiert, sondern eine Liste von einem anderen Speicherort bereitstellt.  
  
 [Vorgehensweise: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben](multiple-controls-bound-to-data-source-synchronized.md)  
 Zeigt, wie das <xref:System.Windows.Forms.BindingSource.BindingComplete>-Ereignis behandelt wird, um sicherzustellen, dass alle an eine Datenquelle gebundenen Steuerelemente synchronisiert bleiben.  
  
 [Vorgehensweise: Stellen Sie sicher, dass die ausgewählte Zeile in einer untergeordneten Tabelle an der richtigen Position verbleibt](ensure-the-selected-row-in-a-child-table-correct.md)  
 Beschreibt, wie Sie sicherstellen können, dass die ausgewählte Zeile in einer untergeordneten Tabelle nicht geändert wird, wenn an einem Feld in der übergeordneten Tabelle eine Änderung vorgenommen wird.  
  
 Siehe auch [im Zusammenhang mit Schnittstellen mit Datenbindung](interfaces-related-to-data-binding.md), [Vorgehensweise: Navigieren durch Daten in Windows Forms](how-to-navigate-data-in-windows-forms.md), und [Vorgehensweise: Erstellen ein einfach gebundenen Steuerelements in einem Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md).  
  
## <a name="reference"></a>Referenz  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 Beschreibt die Klasse, die für die Bindung zwischen einer bindbaren Komponente und einer Datenquelle steht.  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 Beschreibt die Klasse, die eine Datenquelle für die Bindung an Steuerelemente kapselt.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [BindingSource-Komponente](./controls/bindingsource-component.md)  
 Enthält eine Liste mit Themen, in denen gezeigt wird, wie die <xref:System.Windows.Forms.BindingSource>-Komponente verwendet wird.  
  
 [DataGridView-Steuerelement](./controls/datagridview-control-windows-forms.md)  
 Enthält eine Liste mit Themen, in denen gezeigt wird, wie ein bindbares DataGrid-Steuerelement verwendet wird.  
  
 Siehe auch [den Zugriff auf Daten in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).
