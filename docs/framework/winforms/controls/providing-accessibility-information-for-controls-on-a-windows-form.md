---
title: Informationen über Eingabehilfen für Steuerelemente in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
ms.openlocfilehash: 672104db94826cfbe113a7ae0ea29546b0c3b9da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182001"
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a>Informationen über Eingabehilfen für Steuerelemente in Windows Forms
Eingabehilfen sind spezielle Programme und Geräte, die es Personen mit Behinderungen ermöglichen, einen Computer effizienter zu nutzen. Beispiele hierfür sind Sprachausgaben für Blinde sowie Spracheingabe-Hilfsprogramme für Personen, die verbale Befehle geben, statt Maus oder Tastatur zu verwenden. Diese Eingabehilfen interagieren mit den Eingabehilfeeigenschaften, die von Windows Forms-Steuerelementen verfügbar gemacht werden. Diese Eigenschaften sind:  
  
- **AccessibilityObject**  
  
- **AccessibleDefaultActionDescription**  
  
- **AccessibleDescription**  
  
- **AccessibleName**  
  
- **AccessibleRole**  
  
## <a name="accessibilityobject-property"></a>AccessibilityObject-Eigenschaft  
 Diese schreibgeschützte Eigenschaft enthält eine Instanz der <xref:System.Windows.Forms.AccessibleObject> . Die **AccessibleObject** -Klasse implementiert die <xref:Accessibility.IAccessible> -Schnittstelle, die Informationen zur Beschreibung, zur Bildschirmposition, zu den Navigationsfähigkeiten und zum Wert des Steuerelements enthält. Der Entwickler legt diesen Wert fest, wenn das Steuerelement zum Formular hinzugefügt wird.  
  
## <a name="accessibledefaultactiondescription-property"></a>AccessibleDefaultActionDescription-Eigenschaft  
 Diese Zeichenfolge beschreibt die Aktion des Steuerelements. Sie wird nicht im Eigenschaftenfenster angezeigt und kann nur in Code festgelegt werden. Im folgenden Beispiel wird diese Eigenschaft für ein Schaltflächen-Steuerelement (Button) festgelegt.  
  
```vb  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
```

```csharp  
Button1.AccessibleDefaultActionDescription =
   "Closes the application.";  
```

```cpp  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a>Control.AccessibleDescription-Eigenschaft  
 Diese Zeichenfolge beschreibt das Steuerelement. Sie kann im Eigenschaftenfenster oder wie folgt in Code festgelegt werden:  
  
```vb  
Button1.AccessibleDescription = "A button with text 'Exit'."  
```

```csharp  
Button1.AccessibleDescription = "A button with text 'Exit'";  
```

```cpp  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a>Control.AccessibleName-Eigenschaft  
 Diese Eigenschaft enthält den Namen des Steuerelements, der an Eingabehilfen gemeldet wird. Sie kann im Eigenschaftenfenster oder wie folgt in Code festgelegt werden:  
  
```vb  
Button1.AccessibleName = "Order"  
```

```csharp  
Button1.AccessibleName = "Order";  
```

```cpp  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a>AccessibleRole-Eigenschaft  
 Diese Eigenschaft, die eine <xref:System.Windows.Forms.AccessibleRole> enthält, beschreibt die Rolle des Steuerelements in der Benutzeroberfläche. Bei einem neuen Steuerelement ist die Eigenschaft auf `Default` festgelegt. Das heißt, dass sich ein **Schaltflächen** -Steuerelement standardmäßig wie eine **Schaltfläche**verhält. Sie können diese Eigenschaft auf einen anderen Wert festlegen, wenn das jeweilige Steuerelement eine andere Rolle hat. Beispielsweise könnte es sein, dass Sie ein **PictureBox** -Steuerelement als **Diagramm**verwenden und möchten, dass Eingabehilfen die Rolle als **Diagramm**, nicht als **PictureBox**melden. Es ist auch möglich, dass Sie diese Eigenschaft für benutzerdefinierte Steuerelemente angeben, die Sie entwickelt haben. Diese Eigenschaft kann im Eigenschaftenfenster oder wie folgt in Code festgelegt werden:  
  
```vb
PictureBox1.AccessibleRole = AccessibleRole.Chart  
```

```csharp  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
```

```cpp  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
