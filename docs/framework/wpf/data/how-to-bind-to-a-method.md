---
title: "Gewusst wie: Binden an eine Methode | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Bindung, An Methoden"
  - "Klassen, ObjectDataProvider"
  - "Datenbindung, Bindung an Methoden mit ObjectDataProvider"
  - "Methoden, Binden an"
  - "ObjectDataProvider-Klasse"
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Binden an eine Methode
Im folgenden Beispiel wird die Bindung an eine Methode mithilfe von <xref:System.Windows.Data.ObjectDataProvider> veranschaulicht.  
  
## Beispiel  
 In diesem Beispiel ist `TemperatureScale` eine Klasse, die über eine `ConvertTemp`\-Methode verfügt. Auf Grundlage von zwei Parametern \(einer vom Typ `double` und einer vom Typ `enum`\-Typ `TempType)` konvertiert diese Methode den vorgegebenen Wert von einer Temperaturskala in eine andere.  Im folgenden Beispiel wird ein <xref:System.Windows.Data.ObjectDataProvider> verwendet, um das `TemperatureScale`\-Objekt zu instanziieren.  Die `ConvertTemp`\-Methode wird mit zwei angegebenen Parametern aufgerufen.  
  
 [!code-xml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Jetzt ist die Methode als Ressource verfügbar, und Sie können Bindungen an ihre Ergebnisse erstellen.  Im folgenden Beispiel wird die <xref:System.Windows.Controls.TextBox.Text%2A>\-Eigenschaft für das <xref:System.Windows.Controls.TextBox> und für den <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> für das <xref:System.Windows.Controls.ComboBox> an die beiden Parameter der Methode gebunden.  Dies ermöglicht es Benutzern, die zu konvertierende Temperatur sowie die Temperaturskala, aus der konvertiert werden soll, anzugeben.  Beachten Sie, dass <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> auf `true` festgelegt ist, weil die Bindung an die <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A>\-Eigenschaft der <xref:System.Windows.Data.ObjectDataProvider>\-Instanz erfolgt und nicht an Eigenschaften des Objekts, das mit <xref:System.Windows.Data.ObjectDataProvider> umschlossen wird \(das `TemperatureScale`\-Objekt\).  
  
 Der <xref:System.Windows.Controls.ContentControl.Content%2A> der letzten <xref:System.Windows.Controls.Label> wird aktualisiert, sobald der Benutzer den Inhalt für das <xref:System.Windows.Controls.TextBox> oder die Auswahl für das <xref:System.Windows.Controls.ComboBox> ändert.  
  
 [!code-xml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 Der Konverter `DoubleToString` wandelt einen double\-Wert in eine Zeichenfolge in der <xref:System.Windows.Data.IValueConverter.Convert%2A>\-Richtung um \(von der [Bindungsquelle](GTMT) zum [Bindungsziel](GTMT), das in diesem Fall die <xref:System.Windows.Controls.TextBox.Text%2A>\-Eigenschaft ist\), und er wandelt eine `string` in einen `double`\-Wert in der <xref:System.Windows.Data.IValueConverter.ConvertBack%2A>\-Richtung um.  
  
 Die `InvalidationCharacterRule` ist eine <xref:System.Windows.Controls.ValidationRule>, die nach ungültigen Zeichen sucht.  Die Standardfehlervorlage wird durch einen roten Rahmen um das <xref:System.Windows.Controls.TextBox> dargestellt und benachrichtigt den Benutzer, falls es sich beim eingegebenen Wert nicht um einen double\-Wert handelt.  
  
## Siehe auch  
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [Binden an eine Enumeration](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)