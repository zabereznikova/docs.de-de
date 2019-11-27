---
title: End <keyword>-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 87f4724cc036e6e0bdf0b558854a4034f45b9ab5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343740"
---
# <a name="end-keyword-statement-visual-basic"></a>End \<-Schlüsselwort > Anweisung (Visual Basic)

Wenn ein zusätzliches Schlüsselwort folgt, beendet die Definition des von diesem Schlüsselwort eingeführten Anweisungsblocks.

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
  
## <a name="parts"></a>-Komponenten

|-Komponente|Beschreibung|
|---|---|
|`End`|Erforderlich Beendet die Definition des Programmier Elements.|
|`AddHandler`|Erforderlich, um einen `AddHandler` Accessor zu beenden, der durch eine übereinstimmende `AddHandler` Anweisung in einer benutzerdefinierten [Ereignis Anweisung](event-statement.md)gestartet wurde.|
|`Class`|Erforderlich, um eine Klassendefinition zu beenden, die von einer entsprechenden [Class-Anweisung](class-statement.md)gestartet wurde.|
|`Enum`|Erforderlich, um eine Enumerationsdefinition zu beenden, die von einer entsprechenden [enum-Anweisung](enum-statement.md)gestartet wurde.|
|`Event`|Erforderlich, um eine `Custom` Ereignis Definition zu beenden, die von einer entsprechenden [Ereignis Anweisung](event-statement.md)gestartet wurde.|  
|`Function`|Erforderlich, um eine `Function` Prozedur Definition zu beenden, die von einer übereinstimmenden [Funktions Anweisung](function-statement.md)gestartet wurde Wenn die Ausführung auf eine `End Function` Anweisung trifft, wird die Steuerung an den aufrufenden Code zurückgegeben.|
|`Get`|Erforderlich, um eine `Property` Prozedur Definition zu beenden, die von einer passenden [Get-Anweisung](get-statement.md)gestartet wurde. Wenn die Ausführung auf eine `End Get` Anweisung trifft, kehrt die Steuerung zur Anweisung zurück, die den Wert der Eigenschaft anfordert.|
|`If`|Erforderlich, um eine `If`...`Then`...`Else` Block Definition zu beenden, die von einer übereinstimmenden `If` Anweisung gestartet wird. Prüfen Sie, [ob... Dann... Else-Anweisung](if-then-else-statement.md).|
|`Interface`|Erforderlich, um eine Schnittstellen Definition zu beenden, die mit einer übereinstimmenden [Schnittstellen Anweisung](interface-statement.md)begonnen wurde|
|`Module`|Erforderlich, um eine Modul Definition zu beenden, die von einer entsprechenden [Modul Anweisung](module-statement.md)gestartet wurde.|
|`Namespace`|Erforderlich, um eine Namespace Definition zu beenden, die von einer entsprechenden [Namespace-Anweisung](namespace-statement.md)gestartet wurde.|
|`Operator`|Erforderlich, um eine Operator Definition zu beenden, die von einer entsprechenden [Operator Anweisung](operator-statement.md)gestartet wurde.|
|`Property`|Erforderlich, um eine Eigenschafts Definition zu beenden, die von einer entsprechenden [Eigenschafts Anweisung](property-statement.md)gestartet wurde|
|`RaiseEvent`|Erforderlich, um einen `RaiseEvent` Accessor zu beenden, der durch eine übereinstimmende `RaiseEvent` Anweisung in einer benutzerdefinierten [Ereignis Anweisung](event-statement.md)gestartet wurde.|
|`RemoveHandler`|Erforderlich, um einen `RemoveHandler` Accessor zu beenden, der durch eine übereinstimmende `RemoveHandler` Anweisung in einer benutzerdefinierten [Ereignis Anweisung](event-statement.md)gestartet wurde.|
|`Select`|Erforderlich, um eine `Select`...`Case` Block Definition zu beenden, die von einer übereinstimmenden `Select` Anweisung gestartet wird. Siehe [auswählen... Case-Anweisung](select-case-statement.md).  
|`Set`|Erforderlich, um eine `Property` Prozedur Definition zu beenden, die von einer entsprechenden [Set-Anweisung](set-statement.md)gestartet wurde. Wenn die Ausführung auf eine `End Set` Anweisung trifft, kehrt die Steuerung zur-Anweisung zurück, die den Wert der Eigenschaft festlegt.  
|`Structure`|Erforderlich, um eine Struktur Definition zu beenden, die von einer entsprechenden [Structure-Anweisung](structure-statement.md)gestartet wurde.  
|`Sub`|Erforderlich, um eine `Sub` Prozedur Definition zu beenden, die von einer entsprechenden [unter Anweisung](sub-statement.md)gestartet wurde. Wenn die Ausführung auf eine `End Sub` Anweisung trifft, wird die Steuerung an den aufrufenden Code zurückgegeben.  
|`SyncLock`|Erforderlich, um eine `SyncLock` Block Definition zu beenden, die von einer übereinstimmenden `SyncLock` Anweisung gestartet wird Siehe [SyncLock-Anweisung](synclock-statement.md).  
|`Try`|Erforderlich, um eine `Try`...`Catch`...`Finally` Block Definition zu beenden, die von einer übereinstimmenden `Try` Anweisung gestartet wird. Siehe [ausprobieren... Catch... Abschließend-Anweisung](try-catch-finally-statement.md).  
|`While`|Erforderlich, um eine `While` Schleifen Definition zu beenden, die von einer entsprechenden `While` Anweisung gestartet wurde. Siehe [while... End While-Anweisung](while-end-while-statement.md).  
|`With`| Erforderlich, um eine `With` Block Definition zu beenden, die von einer übereinstimmenden `With` Anweisung gestartet wird Weitere Informationen finden Sie [unter... End with-Anweisung](with-end-with-statement.md).  
|||
  
## <a name="directives"></a>Anweisungen

Wenn ein Nummern Zeichen (`#`) vorangestellt ist, beendet das `End`-Schlüsselwort einen Vorverarbeitungs Block, der von der entsprechenden-Direktive eingeführt wird.  

```vb
#End ExternalSource
#End If
#End Region
```

|-Komponente|Beschreibung|
|---|---|
|`#End`|Erforderlich Beendet die Definition des Vorverarbeitungs Blocks.|
|`ExternalSource`|Erforderlich, um einen externen Quell Block zu beenden, der durch eine übereinstimmende [#ExternalSource-Direktive](../directives/externalsource-directive.md)|
|`If`|Erforderlich, um einen Block für die bedingte Kompilierung zu beenden, der durch eine übereinstimmende `#If` Siehe [#If... Dann... #else Direktiven](../directives/if-then-else-directives.md).|
|`Region`|Muss einen Quell Regions Block beenden, der durch eine übereinstimmende [#Region-Direktive](../directives/region-directive.md)gestartet wird.|
|||

## <a name="remarks"></a>Hinweise

Die [End-Anweisung](end-statement.md)ohne zusätzliches Schlüsselwort beendet die Ausführung sofort.

## <a name="smart-device-developer-notes"></a>Entwickler Hinweise zu intelligenten Geräten  

Die `End`-Anweisung ohne zusätzliches Schlüsselwort wird nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [End-Anweisung](end-statement.md)
