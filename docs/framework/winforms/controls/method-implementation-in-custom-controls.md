---
title: Implementierung von Methoden in benutzerdefinierten Steuerelementen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], method implementation
- custom controls [Windows Forms], overloading methods
- custom controls [Windows Forms], method implementation
- methods [Windows Forms]
- methods [Windows Forms], custom controls
ms.assetid: 35d14fca-4bb4-4a27-8211-1f7a98ea27de
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e07d4a5f0a4e66e412b22e1f6cabd24cd81b5ea4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="method-implementation-in-custom-controls"></a>Implementierung von Methoden in benutzerdefinierten Steuerelementen
Eine Methode wird genauso in ein Steuerelement implementiert, wie sie in eine beliebige andere Komponente implementiert würde.  
  
 Wenn es in Visual Basic erforderlich ist, dass eine Methode einen Wert zurückgibt, wird sie als `Public Function` implementiert. Wenn kein Wert zurückgegeben wird, wird sie als `Public Sub` implementiert. Methoden können mithilfe der folgenden Syntax deklariert werden:  
  
```vb  
Public Function ConvertMatterToEnergy(Matter as Integer) As Integer  
   ' Conversion code goes here.  
End Function  
```  
  
 Da Funktionen einen Wert zurückgeben, müssen sie einen Rückgabetyp angeben, beispielsweise ganze Zahl, Zeichenfolge, Objekt usw. Wenn `Function`-Prozeduren oder `Sub`-Prozeduren Argumente übernehmen, müssen diese ebenfalls angegeben werden.  
  
 In C# wird nicht wie in Visual Basic zwischen Funktionen und Prozeduren unterschieden. Von einer Methode wird entweder ein Wert oder `void` zurückgegeben. Die Syntax zum Deklarieren einer öffentlichen C#-Methode lautet:  
  
```csharp  
public int ConvertMatterToEnergy(int matter)  
{  
   // Conversion code goes here.  
}  
```  
  
 Wenn eine Methode deklariert wird, sollten, wenn möglich, alle ihre Argumente als explizite Datentypen deklariert werden. Argumente, die Objektverweise verwenden, sollten als spezielle Klassentypen deklariert werden, z. B. `As Widget` statt `As Object`. In Visual Basic wird die Einhaltung dieser Regel mit der Standardeinstellung `Option Strict` automatisch erzwungen.  
  
 Mit typisierten Argumenten ist es möglich, dass viele Entwicklerfehler bereits vom Compiler und nicht erst zur Laufzeit aufgefangen werden. Fehler werden vom Compiler grundsätzlich aufgefangen, während die Qualität des Laufzeittests von der Art der Testreihe bestimmt wird.  
  
## <a name="overloaded-methods"></a>Überladene Methoden  
 Wenn Benutzer des Steuerelements in der Lage sein sollen, verschiedene Kombinationen von Parametern für Methoden anzugeben, müssen mehrere Überladungen der Methode unter Verwendung expliziter Datentypen bereitgestellt werden. Vermeiden Sie das Erstellen von Parametern, die als `As Object` deklariert sind und beliebige Datentypen enthalten können. Dies könnte zu Fehlern führen, die möglicherweise während des Testens nicht aufgefangen werden.  
  
> [!NOTE]
>  Bei dem universellen Datentyp in der Common Language Runtime handelt es sich um `Object` und nicht um `Variant`. `Variant` wurde aus der Sprache entfernt.  
  
 Mit der `Spin`-Methode eines hypothetischen `Widget`-Steuerelements könnte beispielsweise entweder die direkte Angabe der Richtung und Geschwindigkeit des Drehfelds oder die Angabe eines anderen `Widget`-Objekts ermöglicht werden, von dem das Drehmoment übernommen wird:  
  
```vb  
Overloads Public Sub Spin( _  
   ByVal SpinDirection As SpinDirectionsEnum, _  
   ByVal RevolutionsPerSecond As Double)  
   ' Implementation code here.  
End Sub  
Overloads Public Sub Spin(ByVal Driver As Widget) _  
   ' Implementation code here.  
End Sub  
```  
  
```csharp  
public void Spin(SpinDirectionsEnum spinDirection, double revolutionsPerSecond)  
{  
   // Implementation code here.  
}  
  
public void Spin(Widget driver)  
{  
   // Implementation code here.  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisse](../../../../docs/standard/events/index.md)  
 [Eigenschaften in Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
