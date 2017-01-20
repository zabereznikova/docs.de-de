---
title: "Structure Statement | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Structure"
  - "Structure"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "user-defined types, Structure statement"
  - "compound data types"
  - "Structure keyword"
  - "Structure statement"
  - "UDT (user-defined types)"
  - "types [Visual Basic], user-defined"
ms.assetid: 9bd1deea-2a89-4cdc-812c-6dcbb947c391
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Structure Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Deklariert den Namen einer Struktur und führt die Definitionen der Variablen, Eigenschaften, Ereignisse und Prozeduren ein, aus denen die Struktur besteht.  
  
## Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Partial ] _  
Structure name [ ( Of typelist ) ]  
    [ Implements interfacenames ]  
    [ datamemberdeclarations ]  
    [ methodmemberdeclarations ]  
End Structure  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`attributelist`|Dies ist optional.  Siehe [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Dies ist optional.  Einer der folgenden Werte ist möglich:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Siehe [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Dies ist optional.  Siehe [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`Partial`|Dies ist optional.  Gibt eine partielle Definition der Struktur an.  Siehe [Partial](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Erforderlich.  Name der Struktur.  Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Dies ist optional.  Gibt an, dass dies eine generische Struktur ist.|  
|`typelist`|Erforderlich, wenn Sie das [Of](../../../visual-basic/language-reference/statements/of-clause.md)\-Schlüsselwort verwenden.  Liste mit Typparametern für diese Struktur.  Siehe [Typliste](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Implements`|Dies ist optional.  Gibt an, dass diese Struktur die Member einer oder mehrerer Schnittstellen implementiert.  Siehe [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Erforderlich, wenn Sie die `Implements`\-Anweisung verwenden.  Die Namen der von dieser Struktur implementierten Schnittstellen.|  
|`datamemberdeclarations`|Erforderlich.  Null oder mehrere der Anweisungen `Const`, `Dim`, `Enum` oder `Event`, die *Datenmember* der Struktur deklarieren.|  
|`methodmemberdeclarations`|Dies ist optional.  Null oder mehr Deklarationen der Prozeduren `Function`, `Operator`, `Property` oder `Sub`, die als *Methodenmember* der Struktur fungieren.|  
|`End Structure`|Erforderlich.  Beendet die `Structure`\-Definition.|  
  
## Hinweise  
 Die `Structure`\-Anweisung definiert einen zusammengesetzten Werttyp, den Sie anpassen können.  Eine *Struktur* ist eine Verallgemeinerung des benutzerdefinierten Typs \(UDT, User\-Defined Type\) aus älteren Versionen von Visual Basic.  Weitere Informationen finden Sie unter [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md).  
  
 Strukturen unterstützen viele Funktionen, die auch von Klassen unterstützt werden.  Strukturen können z. B. Eigenschaften und Prozeduren aufweisen, Schnittstellen implementieren und parametrisierte Konstruktoren enthalten.  Allerdings bestehen zwischen Strukturen und Klassen erhebliche Unterschiede in den Bereichen Vererbung, Deklarationen und Verwendung.  Außerdem sind Klassen Verweistypen, und Strukturen sind Werttypen.  Weitere Informationen finden Sie unter [Structures and Classes](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 `Structure` kann nur auf Namespace\- oder Modulebene verwendet werden.  Dies bedeutet, dass der *Deklarationskontext* für eine Struktur eine Quelldatei, ein Namespace, eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein muss und weder eine Prozedur noch ein Block sein kann.  Weitere Informationen finden Sie unter [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Der Standardzugriff für Strukturen ist [Friend](../../../visual-basic/language-reference/modifiers/friend.md).  Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Regeln  
  
-   **Schachtelung.** Sie können eine Struktur in einer anderen Struktur definieren.  Die äußere Struktur wird als *enthaltende Struktur* und die innere Struktur als *geschachtelte Struktur* bezeichnet.  Sie können jedoch nicht über die enthaltende Struktur auf die Member einer geschachtelten Struktur zugreifen.  Stattdessen müssen Sie eine Variable mit dem Datentyp der geschachtelten Struktur deklarieren.  
  
-   **Memberdeklaration.** Sie müssen jeden Member einer Struktur deklarieren.  Ein Strukturmember kann nicht [Protected](../../../visual-basic/language-reference/modifiers/protected.md) oder `Protected Friend` sein, da aus einer Struktur nicht geerbt werden kann.  Die Struktur selbst kann jedoch `Protected` oder `Protected Friend` sein.  
  
     Sie können in einer Struktur null oder mehr nicht freigegebene Variablen oder nicht freigegebene nicht benutzerdefinierte Ereignisse deklarieren.  Es ist nicht möglich, nur Konstanten, Eigenschaften und Prozeduren zu definieren, selbst wenn einige davon nicht gemeinsam genutzt werden.  
  
-   **Initialisierung.** Der Wert von nicht freigegebenen Datenmembern einer Struktur kann nicht als Teil der Deklaration initialisiert werden.  Sie müssen einen solchen Datenmember entweder mit einem parametrisierten Konstruktor auf Strukturebene initialisieren oder dem Member nach dem Erstellen einer Instanz der Struktur einen Wert zuweisen.  
  
-   **Vererbung.** Eine Struktur kann von keinem anderen Typ als von <xref:System.ValueType> erben, von dem alle Strukturen erben.  Insbesondere kann eine Struktur nicht von einer anderen Struktur erben.  
  
     Sie können die [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) nicht in einer Strukturdefinition verwenden, auch nicht zum Angeben von <xref:System.ValueType>.  
  
-   **Implementierung.** Wenn von der Struktur die [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md) verwendet wird, müssen Sie alle Member implementieren, die durch die einzelnen in `interfacenames` angegebenen Schnittstellen definiert sind.  
  
-   **Standardeigenschaft.** Für eine Struktur kann höchstens eine Eigenschaft als *Standardeigenschaft* angegeben werden. Verwenden Sie hierzu den Modifizierer [Default](../../../visual-basic/language-reference/modifiers/default.md).  Weitere Informationen finden Sie unter [Default](../../../visual-basic/language-reference/modifiers/default.md).  
  
## Verhalten  
  
-   **Zugriffsebene.** In einer Struktur können Sie jeden Member mit einer eigenen Zugriffsebene deklarieren.  Der Standardzugriff für alle Strukturmember ist [Public](../../../visual-basic/language-reference/modifiers/public.md).  Beachten Sie, dass der Zugriff auf die Member einer Struktur automatisch eingeschränkt ist, wenn die Struktur selbst über eine restriktivere Zugriffsebene verfügt, selbst wenn Sie die Zugriffsebenen der Member mit den Zugriffsmodifizierern anpassen.  
  
-   **Bereich.** Der Gültigkeitsbereich einer Struktur umfasst den Namespace, die Klasse, Struktur oder das Modul, in dem bzw. der sich die Struktur befindet.  
  
     Der Gültigkeitsbereich eines Strukturmembers umfasst die gesamte Struktur.  
  
-   **Lebensdauer.** Eine Struktur selbst verfügt nicht über eine Lebensdauer.  Stattdessen verfügt jede Instanz der Struktur über eine Lebensdauer, die von allen anderen Instanzen unabhängig ist.  
  
     Die Lebensdauer einer Instanz beginnt mit ihrer Erstellung durch eine [New Operator](../../../visual-basic/language-reference/operators/new-operator.md)\-Klausel.  Sie endet, wenn die enthaltende Lebensdauer der Variablen endet.  
  
     Sie können die Lebensdauer einer Strukturinstanz nicht verlängern.  Eine den Funktionen einer statischen Struktur ähnelnde Funktionalität wird von einem Modul bereitgestellt.  Weitere Informationen finden Sie unter [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Strukturmember verfügen über eine Lebensdauer, die davon abhängt, wie und wo sie deklariert werden.  Weitere Informationen finden Sie in [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) unter "Lebensdauer".  
  
-   **Qualifikation.** In Code außerhalb einer Struktur muss der Name eines Members mit dem Namen dieser Struktur qualifiziert werden.  
  
     Wenn Code in einer geschachtelten Struktur einen nicht qualifizierten Verweis auf ein Programmierelement enthält, wird von Visual Basic das Element zunächst in der geschachtelten Struktur gesucht, anschließend in der enthaltenden Struktur und so weiter bis zum äußersten enthaltenden Element.  Weitere Informationen finden Sie unter [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
-   **Speicherverbrauch.** Wie bei allen zusammengesetzten Datentypen können Sie den gesamten Speicherverbrauch auch bei Strukturen nicht dadurch zuverlässig berechnen, indem Sie die nominalen Speicherbelegungen ihrer Member addieren.  Darüber hinaus können Sie nicht davon ausgehen, dass die Member im Speicher in derselben Reihenfolge wie in der Deklaration angeordnet sind.  Wenn Sie das Speicherlayout einer Struktur steuern müssen, können Sie das <xref:System.Runtime.InteropServices.StructLayoutAttribute>\-Attribut auf die `Structure`\-Anweisung anwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird die `Structure`\-Anweisung für die Definition einer Gruppe verknüpfter Daten für einen Mitarbeiter verwendet.  Es veranschaulicht die Verwendung von Membern mit dem Zugriff `Public`, `Friend` und `Private`, um den Grad der Vertraulichkeit der Datenelemente anzugeben.  Es zeigt außerdem Prozedur\-, Eigenschaften\- und Ereignismember.  
  
 [!code-vb[VbVbalrStatements#57](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/structure-statement_1.vb)]  
  
## Siehe auch  
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md)   
 [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Structures and Classes](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)