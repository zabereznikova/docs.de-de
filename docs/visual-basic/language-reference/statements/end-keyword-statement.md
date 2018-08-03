---
title: End &lt;Schlüsselwort&gt; Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 8137434bfd8c26144d78b1761b784cdba4894eaf
ms.sourcegitcommit: 7fe772c6c05a982153655d618c826e9839d39cac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2018
ms.locfileid: "33605263"
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a>End &lt;Schlüsselwort&gt; Anweisung (Visual Basic)

Wenn Sie ein zusätzliches Schlüsselwort gefolgt wird, beendet die Definition der Anweisungsblock, der durch dieses Schlüsselwort eingeführt.

## <a name="syntax"></a>Syntax

```vb
End AddHandler
End Class
End Enum
End Event
End Function
End Get
End If
End Interface
End Module
End Namespace
End Operator
End Property
End RaiseEvent  
End RemoveHandler  
End Select
End Set
End Structure
End Sub
End SyncLock
End Try
End While
End With  
```  
  
## <a name="parts"></a>Teile

|Segment|Beschreibung|
|---|---|
|`End`|Erforderlich. Beendet die Definition des Programmierelements.|
|`AddHandler`|Erforderlich, um eine `AddHandler` Accessor begonnen, die durch eine entsprechende `AddHandler` Anweisung in einem benutzerdefinierten [Event-Anweisung](event-statement.md).|
|`Class`|Erforderlich, um eine Klassendefinition durch eine entsprechende begonnen [Class-Anweisung](class-statement.md).|
|`Enum`|Erforderlich, um eine aufzählungsdefinition begonnen, die durch eine entsprechende [Enum-Anweisung](enum-statement.md).|
|`Event`|Erforderlich, um eine `Custom` Ereignisdefinition begonnen, die durch eine entsprechende [Event-Anweisung](event-statement.md).|  
|`Function`|Erforderlich, um eine `Function` Definition der Prozedur durch eine entsprechende begonnen [Function-Anweisung](function-statement.md). Wenn die Ausführung findet eine `End Function` -Anweisung, die Steuerung an den aufrufenden Code zurückgegeben.|
|`Get`|Erforderlich, um eine `Property` Definition der Prozedur durch eine entsprechende begonnen [Get Statement](get-statement.md). Wenn die Ausführung findet eine `End Get` -Anweisung, die Steuerung an die Anweisung, die Anforderung den Wert der Eigenschaft zurückgegeben.|
|`If`|Erforderlich, um eine `If`... `Then`... `Else` -Blockdefinition durch eine entsprechende `If` Anweisung. Finden Sie unter [Wenn... Klicken Sie dann... Else-Anweisung](if-then-else-statement.md).|
|`Interface`|Erforderlich, um eine Schnittstellendefinition begonnen, die durch eine entsprechende [Interface-Anweisung](interface-statement.md).|
|`Module`|Erforderlich, um eine angefangene durch eine entsprechende Moduldefinition [Module-Anweisung](module-statement.md).|
|`Namespace`|Erforderlich, um eine Namespace-Definition, die durch eine entsprechende begonnen [Namespace-Anweisung](namespace-statement.md).|
|`Operator`|Erforderlich, um eine Operatordefinition begonnen, die durch eine entsprechende [Operator-Anweisung](operator-statement.md).|
|`Property`|Erforderlich, um eine Eigenschaftsdefinition begonnen, die durch eine entsprechende [Property Statement](property-statement.md).|
|`RaiseEvent`|Erforderlich, um eine `RaiseEvent` Accessor begonnen, die durch eine entsprechende `RaiseEvent` Anweisung in einem benutzerdefinierten [Event-Anweisung](event-statement.md).|
|`RemoveHandler`|Erforderlich, um eine `RemoveHandler` Accessor begonnen, die durch eine entsprechende `RemoveHandler` Anweisung in einem benutzerdefinierten [Event-Anweisung](event-statement.md).|
|`Select`|Erforderlich, um eine `Select`... `Case` -Blockdefinition durch eine entsprechende `Select` Anweisung. Finden Sie unter [auswählen... Case-Anweisung](select-case-statement.md).  
|`Set`|Erforderlich, um eine `Property` Definition der Prozedur durch eine entsprechende begonnen [Set-Anweisung](set-statement.md). Wenn die Ausführung findet eine `End Set` -Anweisung, die Steuerung an die Anweisung aus, durch den Wert der Eigenschaft zurückgegeben.  
|`Structure`|Erforderlich, um eine angefangene durch eine entsprechende Strukturdefinition [Structure-Anweisung](structure-statement.md).  
|`Sub`|Erforderlich, um eine `Sub` Definition der Prozedur durch eine entsprechende begonnen [Sub-Anweisung](sub-statement.md). Wenn die Ausführung findet eine `End Sub` -Anweisung, die Steuerung an den aufrufenden Code zurückgegeben.  
|`SyncLock`|Erforderlich, um eine `SyncLock` -Blockdefinition durch eine entsprechende `SyncLock` Anweisung. Finden Sie unter [SyncLock-Anweisung](synclock-statement.md).  
|`Try`|Erforderlich, um eine `Try`... `Catch`... `Finally` -Blockdefinition durch eine entsprechende `Try` Anweisung. Finden Sie unter [testen... Catch... Finally-Anweisung](try-catch-finally-statement.md).  
|`While`|Erforderlich, um eine `While` Schleife begonnen, die durch eine entsprechende Definition `While` Anweisung. Finden Sie unter [während... While-Anweisung enden](while-end-while-statement.md).  
|`With`| Erforderlich, um eine `With` -Blockdefinition durch eine entsprechende `With` Anweisung. Finden Sie unter [mit... With-Anweisung](with-end-with-statement.md).  
|||
  
## <a name="directives"></a>Anweisungen

Wenn Sie mit einem Nummernzeichen (`#`), wird die `End` Schlüsselwort beendet ein Präprozessorblock eingeführt, durch die entsprechende Direktive.  

```vb
#End ExternalSource
#End If
#End Region
```

|Segment|Beschreibung|
|---|---|
|`#End`|Erforderlich. Beendet die Definition des vorverarbeitung-Blocks.|
|`ExternalSource`|Erforderlich, um einen externen Quellblock begonnen, die durch eine entsprechende [#ExternalSource-Anweisung](../directives/externalsource-directive.md).|
|`If`|Erforderlich, um einen für die bedingte Kompilierung-Block, der durch eine entsprechende begonnen `#If` Richtlinie. Finden Sie unter [#If... ... #Else-Anweisungen](../directives/if-then-else-directives.md).|
|`Region`|Erforderlich, um ein Quellblock zu Region beenden durch eine entsprechende [#Region-Anweisung](../directives/region-directive.md).|
|||

## <a name="remarks"></a>Hinweise

Die [End-Anweisung](end-statement.md), ohne zusätzliche Schlüsselwort beendet die Ausführung sofort.

## <a name="smart-device-developer-notes"></a>Hinweise für Entwickler intelligente Geräte  

Die `End` Anweisung, ohne zusätzliche Schlüsselwort wird nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

[End-Anweisung](end-statement.md)
