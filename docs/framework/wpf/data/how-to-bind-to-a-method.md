---
title: 'Gewusst wie: Binden an eine Methode'
description: In diesem Beispiel erfahren Sie, wie Sie eine Bindung an die-Methode eines Objekts in der Windows Presentation Foundation (WPF) durchführen.
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
ms.openlocfilehash: 9501e6357203c21651e85f1d65059be1d70becf2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619597"
---
# <a name="how-to-bind-to-a-method"></a>Gewusst wie: Binden an eine Methode
Im folgenden Beispiel wird gezeigt, wie mithilfe von eine Bindung an eine Methode hergestellt wird <xref:System.Windows.Data.ObjectDataProvider> .  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel ist `TemperatureScale` eine Klasse, die über eine `ConvertTemp`-Methode verfügt. Auf Grundlage von zwei Parametern (einem des Typs `double` und einem des `enum`-Typs `TempType)`) konvertiert diese Methode den vorgegebenen Wert von einer Temperaturskala in eine andere. Im folgenden Beispiel wird ein- <xref:System.Windows.Data.ObjectDataProvider> Objekt verwendet, um das-Objekt zu instanziieren `TemperatureScale` . Die `ConvertTemp`-Methode wird mit zwei angegebenen Parametern aufgerufen.  
  
 [!code-xaml[BindToMethod#WindowResources](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Nun da die Methode als Ressource verfügbar ist, können Sie Bindungen an ihre Ergebnisse erstellen. Im folgenden Beispiel <xref:System.Windows.Controls.TextBox.Text%2A> werden die-Eigenschaft des <xref:System.Windows.Controls.TextBox> und des-Objekts <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> <xref:System.Windows.Controls.ComboBox> an die beiden Parameter der-Methode gebunden. Dies ermöglicht Benutzern, die zu konvertierende Temperatur sowie die Temperaturskala anzugeben, aus der konvertiert werden soll. Beachten Sie, dass <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> auf festgelegt ist, `true` da wir an die <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> -Eigenschaft der <xref:System.Windows.Data.ObjectDataProvider> -Instanz und nicht an die Eigenschaften des Objekts gebunden sind, das von der <xref:System.Windows.Data.ObjectDataProvider> (dem- `TemperatureScale` Objekt) umschließt wird  
  
 Der <xref:System.Windows.Controls.ContentControl.Content%2A> der letzten <xref:System.Windows.Controls.Label> Updates, wenn der Benutzer den Inhalt von <xref:System.Windows.Controls.TextBox> oder die Auswahl von ändert <xref:System.Windows.Controls.ComboBox> .  
  
 [!code-xaml[BindToMethod#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 Der Konverter `DoubleToString` nimmt einen Double-Wert und wandelt ihn in eine Zeichenfolge in die <xref:System.Windows.Data.IValueConverter.Convert%2A> Richtung (von der Bindungs Quelle zum Bindungs Ziel, die die- <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft ist) und konvertiert einen `string` `double` in die <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> Richtung.  
  
 Der `InvalidationCharacterRule` ist ein <xref:System.Windows.Controls.ValidationRule> , der auf ungültige Zeichen prüft. Die Standardfehler Vorlage, bei der es sich um einen roten Rahmen um handelt <xref:System.Windows.Controls.TextBox> , wird angezeigt, um Benutzer zu benachrichtigen, wenn der Eingabe Wert kein doppelter Wert ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Artikel zu Vorgehensweisen](data-binding-how-to-topics.md)
- [Binden an eine Enumeration](how-to-bind-to-an-enumeration.md)
