---
title: 'Vorgehensweise: Binden an eine Methode'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
ms.openlocfilehash: 6cdad46fd6d9ef3bc4ce1a13fedb6ff1d639d93e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123239"
---
# <a name="how-to-bind-to-a-method"></a>Vorgehensweise: Binden an eine Methode
Das folgende Beispiel zeigt, wie zum Binden an eine Methode mit <xref:System.Windows.Data.ObjectDataProvider>.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel ist `TemperatureScale` eine Klasse, die über eine `ConvertTemp`-Methode verfügt. Auf Grundlage von zwei Parametern (einem des Typs `double` und einem des `enum`-Typs `TempType)`) konvertiert diese Methode den vorgegebenen Wert von einer Temperaturskala in eine andere. Im folgenden Beispiel eine <xref:System.Windows.Data.ObjectDataProvider> wird zum Instanziieren der `TemperatureScale` Objekt. Die `ConvertTemp`-Methode wird mit zwei angegebenen Parametern aufgerufen.  
  
 [!code-xaml[BindToMethod#WindowResources](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Nun da die Methode als Ressource verfügbar ist, können Sie Bindungen an ihre Ergebnisse erstellen. Im folgenden Beispiel die <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft der <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> von der <xref:System.Windows.Controls.ComboBox> an die beiden Parameter der Methode gebunden sind. Dies ermöglicht Benutzern, die zu konvertierende Temperatur sowie die Temperaturskala anzugeben, aus der konvertiert werden soll. Beachten Sie, dass <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> nastaven NA hodnotu `true` , da wir eine Bindung der <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> Eigenschaft der <xref:System.Windows.Data.ObjectDataProvider> -Instanz und nicht die Eigenschaften des Objekts eingeschlossen werden, indem Sie die <xref:System.Windows.Data.ObjectDataProvider> (der `TemperatureScale` Objekt).  
  
 Die <xref:System.Windows.Controls.ContentControl.Content%2A> des letzten <xref:System.Windows.Controls.Label> aktualisiert, wenn der Benutzer den Inhalt des ändert die <xref:System.Windows.Controls.TextBox> oder die Auswahl für die <xref:System.Windows.Controls.ComboBox>.  
  
 [!code-xaml[BindToMethod#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 Der Konverter `DoubleToString` nimmt einen Double-Wert und erstellt daraus in eine Zeichenfolge in die <xref:System.Windows.Data.IValueConverter.Convert%2A> Richtung (von der Bindungsquelle zum Bindungsziel, d.h. die <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft) und konvertiert ein `string` auf eine `double` in die <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> Richtung.  
  
 Die `InvalidationCharacterRule` ist eine <xref:System.Windows.Controls.ValidationRule> , die nach ungültigen Zeichen sucht. Die Standardvorlage für die Fehler, die einen roten Rahmen ist rund um die <xref:System.Windows.Controls.TextBox>, angezeigt wird, um Benutzer zu benachrichtigen, wenn der Eingabewert nicht um einen double-Wert ist.  
  
## <a name="see-also"></a>Siehe auch

- [Gewusst wie-Themen](data-binding-how-to-topics.md)
- [Binden an eine Enumeration](how-to-bind-to-an-enumeration.md)
