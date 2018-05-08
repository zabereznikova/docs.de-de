---
title: 'Gewusst wie: Binden an eine Methode'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
ms.openlocfilehash: 58e243812f9c2dcb65dc37bfd50d9bcfb124e4f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bind-to-a-method"></a>Gewusst wie: Binden an eine Methode
Im folgende Beispiel wird gezeigt, wie zum Binden an eine Methode mit <xref:System.Windows.Data.ObjectDataProvider>.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel ist `TemperatureScale` eine Klasse, die über eine `ConvertTemp`-Methode verfügt. Auf Grundlage von zwei Parametern (einem des Typs `double` und einem des `enum`-Typs `TempType)`) konvertiert diese Methode den vorgegebenen Wert von einer Temperaturskala in eine andere. Im folgenden Beispiel ein <xref:System.Windows.Data.ObjectDataProvider> wird zum Instanziieren der `TemperatureScale` Objekt. Die `ConvertTemp`-Methode wird mit zwei angegebenen Parametern aufgerufen.  
  
 [!code-xaml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Nun da die Methode als Ressource verfügbar ist, können Sie Bindungen an ihre Ergebnisse erstellen. Im folgenden Beispiel die <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft von der <xref:System.Windows.Controls.TextBox> und die <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> von der <xref:System.Windows.Controls.ComboBox> an die beiden Parameter der Methode gebunden sind. Dies ermöglicht Benutzern, die zu konvertierende Temperatur sowie die Temperaturskala anzugeben, aus der konvertiert werden soll. Beachten Sie, dass <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> auf festgelegt ist `true` da wir zum Binden der <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> Eigenschaft von der <xref:System.Windows.Data.ObjectDataProvider> Instanz und nicht die Eigenschaften des Objekts umschlossen der <xref:System.Windows.Data.ObjectDataProvider> (die `TemperatureScale` Objekt).  
  
 Die <xref:System.Windows.Controls.ContentControl.Content%2A> des letzten <xref:System.Windows.Controls.Label> aktualisiert, wenn der Benutzer den Inhalt des ändert die <xref:System.Windows.Controls.TextBox> oder die Auswahl für die <xref:System.Windows.Controls.ComboBox>.  
  
 [!code-xaml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 Der Konverter `DoubleToString` akzeptiert einen Double und verwandelt sie in eine Zeichenfolge in der <xref:System.Windows.Data.IValueConverter.Convert%2A> Richtung (von der Bindungsquelle zum Bindungsziel, also die <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft) und konvertiert eine `string` auf eine `double` in der <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> Richtung.  
  
 Die `InvalidationCharacterRule` ist eine <xref:System.Windows.Controls.ValidationRule> , die überprüft, ob ein ungültiges Zeichen. Die Standardvorlage für die Fehler, also einen roten Rahmen um das <xref:System.Windows.Controls.TextBox>, angezeigt wird, um Benutzer zu benachrichtigen, wenn der Eingabewert keinen double-Wert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [Binden an eine Enumeration](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)
