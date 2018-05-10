---
title: End &lt;Schlüsselwort&gt; -Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 8137434bfd8c26144d78b1761b784cdba4894eaf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a>End &lt;Schlüsselwort&gt; -Anweisung (Visual Basic)
Wenn ein zusätzliches Schlüsselwort folgt, beendet die Definition des der Anweisungsblock durch dieses Schlüsselwort eingeführt.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 `End`  
 Erforderlich. Beendet die Definition des Programmierelements.  
  
 `AddHandler`  
 Erforderlich, um eine `AddHandler` Zugriffsmethode, die durch eine entsprechende begonnen `AddHandler` -Anweisung in einer benutzerdefinierten [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Class`  
 Erforderlich, um die Definition einer Klasse, durch eine entsprechende begonnen [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md).  
  
 `Enum`  
 Erforderlich, um eine durch eine entsprechende begonnen aufzählungsdefinition [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 `Event`  
 Erforderlich, um eine `Custom` Ereignisdefinition begonnen, die durch eine entsprechende [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Function`  
 Erforderlich, um eine `Function` Prozedurdefinition durch eine entsprechende begonnen [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md). Wenn die Ausführung findet eine `End``Function` -Anweisung, die Steuerung an den aufrufenden Code zurückgegeben.  
  
 `Get`  
 Erforderlich, um eine `Property` Prozedurdefinition durch eine entsprechende begonnen [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md). Wenn die Ausführung findet eine `End``Get` -Anweisung, die Steuerung an die Anweisung mit dem Wert der Eigenschaft angefordert zurückgegeben.  
  
 `If`  
 Erforderlich, um eine `If`... `Then`... `Else` -Blockdefinition durch eine entsprechende `If` Anweisung. Finden Sie unter [Wenn... Dann... Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md).  
  
 `Interface`  
 Erforderlich, um eine durch eine entsprechende angefangene Schnittstellendefinition [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md).  
  
 `Module`  
 Erforderlich, um eine durch eine entsprechende angefangene Moduldefinition [Modulanweisung](../../../visual-basic/language-reference/statements/module-statement.md).  
  
 `Namespace`  
 Erforderlich, um eine durch eine entsprechende angefangene Namespacedefinition [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md).  
  
 `Operator`  
 Erforderlich, um eine Operatordefinition begonnen, die durch eine entsprechende [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 `Property`  
 Erforderlich, um eine Eigenschaftsdefinition durch eine entsprechende begonnen [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md).  
  
 `RaiseEvent`  
 Erforderlich, um eine `RaiseEvent` Zugriffsmethode, die durch eine entsprechende begonnen `RaiseEvent` -Anweisung in einer benutzerdefinierten [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `RemoveHandler`  
 Erforderlich, um eine `RemoveHandler` Zugriffsmethode, die durch eine entsprechende begonnen `RemoveHandler` -Anweisung in einer benutzerdefinierten [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).  
  
 `Select`  
 Erforderlich, um eine `Select`... `Case` -Blockdefinition durch eine entsprechende `Select` Anweisung. Finden Sie unter [auswählen... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
 `Set`  
 Erforderlich, um eine `Property` Prozedurdefinition durch eine entsprechende begonnen [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md). Wenn die Ausführung findet eine `End``Set` -Anweisung, die Steuerung an die Anweisung aus, durch den Wert der Eigenschaft zurückgegeben.  
  
 `Structure`  
 Erforderlich, um eine durch eine entsprechende angefangene Strukturdefinition [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md).  
  
 `Sub`  
 Erforderlich, um eine `Sub` Prozedurdefinition durch eine entsprechende begonnen [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md). Wenn die Ausführung findet eine `End``Sub` -Anweisung, die Steuerung an den aufrufenden Code zurückgegeben.  
  
 `SyncLock`  
 Erforderlich, um eine `SyncLock` -Blockdefinition durch eine entsprechende `SyncLock` Anweisung. Finden Sie unter [SyncLock-Anweisung](../../../visual-basic/language-reference/statements/synclock-statement.md).  
  
 `Try`  
 Erforderlich, um eine `Try`... `Catch`... `Finally` -Blockdefinition durch eine entsprechende `Try` Anweisung. Finden Sie unter [versuchen... Catch... Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 `While`  
 Erforderlich, um eine `While` Schleife begonnen, die durch eine entsprechende Definition `While` Anweisung. Finden Sie unter [während... While-Anweisung enden](../../../visual-basic/language-reference/statements/while-end-while-statement.md).  
  
 `With`  
 Erforderlich, um eine `With` -Blockdefinition durch eine entsprechende `With` Anweisung. Finden Sie unter [mit... With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## <a name="remarks"></a>Hinweise  
 Die [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md), ohne zusätzliche Schlüsselwort beendet die Ausführung sofort.  
  
 Wenn ein Nummernzeichen vorangestellt (`#`), wird die `End` Schlüsselwort beendet einen vorab verarbeitetes Block, der durch die entsprechende Richtlinie eingeführt.  
  
 `#End`  
 Erforderlich. Beendet die Definition des Präprozessorlauf Blocks.  
  
 `#ExternalSource`  
 Erforderlich, um einen externen Quellblock begonnen, die durch eine entsprechende [#ExternalSource-Direktive](../../../visual-basic/language-reference/directives/externalsource-directive.md).  
  
 `#If`  
 Erforderlich, um eine bedingte Kompilierung-Block, der durch eine entsprechende begonnen `#If` Richtlinie. Finden Sie unter [#If... ... #Else-Direktiven](../../../visual-basic/language-reference/directives/if-then-else-directives.md).  
  
 `#Region`  
 Erforderlich, um ein Quellblock-Region durch eine entsprechende begonnen [#Region-Direktive](../../../visual-basic/language-reference/directives/region-directive.md).  
  
## <a name="smart-device-developer-notes"></a>Entwicklerhinweise für intelligente Geräte  
 Die `End` -Anweisung ohne zusätzliche Schlüsselwort wird nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md)
