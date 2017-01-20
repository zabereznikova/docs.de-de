---
title: "Interface Statement (Visual Basic) | Microsoft Docs"
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
  - "vb.Interface"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interface statement [Visual Basic]"
  - "interfaces, interface definition"
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
caps.latest.revision: 26
caps.handback.revision: 26
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Interface Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Deklariert den Namen einer Schnittstelle und führt die Definitionen der Member ein, die die Schnittstelle umfasst.  
  
## Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] _  
Interface name [ ( Of typelist ) ]  
    [ Inherits interfacenames ]  
    [ [ modifiers ] Property membername ]  
    [ [ modifiers ] Function membername ]  
    [ [ modifiers ] Sub membername ]  
    [ [ modifiers ] Event membername ]  
    [ [ modifiers ] Interface membername ]  
    [ [ modifiers ] Class membername ]  
    [ [ modifiers ] Structure membername ]  
End Interface  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`attributelist`|Optional.  Siehe [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Optional.  Einer der folgenden Werte ist möglich:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Optional.  Siehe [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`name`|Erforderlich.  Name dieser Schnittstelle.  Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Optional.  Gibt an, dass dies eine generische Schnittstelle ist.|  
|`typelist`|Erforderlich, wenn Sie das [Of](../../../visual-basic/language-reference/statements/of-clause.md)\-Schlüsselwort verwenden.  Liste mit Typparametern für diese Schnittstelle.  Optional kann jeder Typparameter mit dem generischen `In`\-Modifizierer und dem generischen `Out`\-Modifizierer als Variant deklariert werden.  Siehe [Typliste](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Optional.  Gibt an, dass diese Schnittstelle die Attribute und die Member von anderen Schnittstellen erbt.  Weitere Informationen finden Sie unter [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`interfacenames`|Erforderlich, wenn Sie die `Inherits`\-Anweisung verwenden.  Die Namen der Schnittstellen, von denen diese Schnittstelle abgeleitet wird.|  
|`modifiers`|Optional.  Entsprechende Modifizierer für den zu definierenden Schnittstellenmember.|  
|`Property`|Optional.  Definiert eine Eigenschaft, die ein Member der Schnittstelle ist.|  
|`Function`|Optional.  Definiert eine `Function`\-Prozedur, die ein Member der Schnittstelle ist.|  
|`Sub`|Optional.  Definiert eine `Sub`\-Prozedur, die ein Member der Schnittstelle ist.|  
|`Event`|Optional.  Definiert ein Ereignis, das ein Member der Schnittstelle ist.|  
|`Interface`|Optional.  Definiert eine Schnittstelle, die in dieser Schnittstelle geschachtelt ist.  Die Definition der geschachtelten Schnittstelle muss mit einer `End Interface`\-Anweisung enden.|  
|`Class`|Optional.  Definiert eine Klasse, die ein Member der Schnittstelle ist.  Die Klassendefinition des Members muss mit einer `End Class`\-Anweisung enden.|  
|`Structure`|Optional.  Definiert eine Struktur, die ein Member der Schnittstelle ist.  Die Strukturdefinition des Members muss mit einer `End Structure`\-Anweisung enden.|  
|`membername`|Für jede Eigenschaft, jede Prozedur, jedes Ereignis, jede Schnittstelle, jede Klasse oder Struktur erforderlich, die als Member der Schnittstelle definiert ist.  Der Name des Members.|  
|`End Interface`|Beendet die `Interface`\-Definition.|  
  
## Hinweise  
 Eine *Schnittstelle* definiert einen Satz von Membern, z. B. Eigenschaften und Prozeduren, die von Klassen und Strukturen implementiert werden können.  Die Schnittstelle definiert nur die Signaturen der Member und nicht ihre interne Ausführung.  
  
 Eine Klasse oder Struktur implementiert die Schnittstelle, indem sie Code für jeden Member angibt, der durch die Schnittstelle definiert wird.  Wenn die Anwendung eine Instanz aus dieser Klasse oder Struktur erstellt, ist schließlich ein Objekt im Speicher vorhanden, das ausgeführt wird.  Weitere Informationen finden Sie unter [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) und [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 `Interface` kann nur auf Namespace\- oder Modulebene verwendet werden.  Dies bedeutet, dass der *Deklarationskontext* für eine Schnittstelle eine Quelldatei, ein Namespace, eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein muss und weder eine Prozedur noch ein Block sein kann.  Weitere Informationen finden Sie unter [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Die Standardzugriffsebene für Schnittstellen ist [Friend](../../../visual-basic/language-reference/modifiers/friend.md).  Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Regeln  
  
-   **Schachteln von Schnittstellen.** Sie können eine Schnittstelle in einer anderen Schnittstelle definieren.  Die äußere Schnittstelle wird als *enthaltende Schnittstelle* und die innere Schnittstelle als *geschachtelte Schnittstelle* bezeichnet.  
  
-   **Memberdeklaration.** Wenn Sie eine Eigenschaft oder Prozedur als Member einer Schnittstelle deklarieren, definieren Sie nur die *Signatur* der betreffenden Eigenschaft oder Prozedur.  Diese umfasst den Elementtyp \(Eigenschaft oder Prozedur\), ihre Parameter und Parametertypen und ihren Rückgabetyp.  Aus diesem Grund erfolgt die Memberdefinition in einer einzigen Codezeile, und Anweisungen zum Beenden, z. B. `End Function` oder `End Property`, sind in Schnittstellen nicht gültig.  
  
     Wenn Sie hingegen eine Enumeration, eine Struktur, eine geschachtelte Klasse oder geschachtelte Schnittstelle definieren, müssen ihre Datenmember in der Definition enthalten sein.  
  
-   **Membermodifizierer.** Beim Definieren von Modulmembern können Sie keine Zugriffsmodifizierer verwenden, und Sie können weder [Shared](../../../visual-basic/language-reference/modifiers/shared.md) noch einen anderen Prozedurmodifizierer außer [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md) angeben.  Sie können jeden Member mit [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) deklarieren, und Sie können [Default](../../../visual-basic/language-reference/modifiers/default.md) sowie [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) und [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md) beim Definieren einer Eigenschaft verwenden.  
  
-   **Vererbung.** Wenn die Schnittstelle das [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) verwendet, können Sie eine oder mehrere Basisschnittstellen angeben.  Sie können zwei Schnittstellen vererben, auch wenn jede Schnittstelle einen Member mit dem gleichen Namen definiert.  In diesem Fall muss der implementierende Code Namensqualifizierung verwenden, um anzugeben, welcher Member implementiert wird.  
  
     Eine Schnittstelle kann nicht von einer anderen Schnittstelle mit einer restriktiveren Zugriffsebene erben.  Eine Schnittstelle mit `Public`\-Zugriff kann beispielweise nicht von einer Schnittstelle mit `Friend`\-Zugriff erben.  
  
     Eine Schnittstelle kann nicht von einer Schnittstelle erben, die in ihr geschachtelt ist.  
  
-   **Implementierung.** Wenn eine Klasse die [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)\-Anweisung verwendet, um eine Schnittstelle zu implementieren, muss sie jeden in der Schnittstelle definierten Member implementieren.  Außerdem muss jede Signatur im implementierenden Code genau mit der entsprechenden Signatur übereinstimmen, die in dieser Schnittstelle definiert ist.  Der Name des Members im implementierenden Code muss jedoch nicht mit dem in der Schnittstelle definierten Membernamen übereinstimmen.  
  
     Wenn eine Klasse eine Prozedur implementiert, kann sie die Prozedur nicht als `Shared` festlegen.  
  
-   **Standardeigenschaft.** Für eine Schnittstelle kann höchstens eine Eigenschaft als *Standardeigenschaft* angegeben werden, auf die ohne Angabe des Eigenschaftennamens verwiesen werden kann.  Sie geben eine solche Eigenschaft an, indem Sie sie mit dem [Default](../../../visual-basic/language-reference/modifiers/default.md)\-Modifizierer deklarieren.  
  
     Beachten Sie, dass daher eine Schnittstelle nur eine Standardeigenschaft definieren kann, wenn sie keine Standardeigenschaft erbt.  
  
## Verhalten  
  
-   **Zugriffsebene.** Alle Schnittstellenmember verfügen implizit über [Public](../../../visual-basic/language-reference/modifiers/public.md)\-Zugriff.  Sie können keinen Zugriffsmodifizierer verwenden, wenn Sie einen Member definieren.  Eine Klasse jedoch, die die Schnittstelle implementiert, kann für jeden implementierten Member eine Zugriffsebene deklarieren.  
  
     Wenn Sie einer Variablen eine Klasseninstanz zuweisen, kann die Zugriffsebene ihrer Member davon abhängen, ob der Datentyp der Variablen die zugrunde liegende Schnittstelle oder die implementierende Klasse ist.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
     [!code-vb[VbVbalrStatements#39](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_1.vb)]  
  
     Wenn Sie auf Klassenmember über `varAsInterface` zugreifen, weisen sie alle öffentlichen Zugriff auf.  Wenn Sie jedoch auf Member über `varAsClass` zugreifen, weist die `Sub`\-Prozedur `doSomething` privaten Zugriff auf.  
  
-   **Gültigkeitsbereich.** Der Gültigkeitsbereich einer Schnittstelle umfasst ihren Namespace, ihre Klasse, ihre Struktur oder ihr Modul.  
  
     Der Gültigkeitsbereich jedes Schnittstellenmembers umfasst die gesamte Schnittstelle.  
  
-   **Lebensdauer.** Weder Schnittstellen noch ihre Member verfügen über eine Lebensdauer.  Wenn eine Klasse eine Schnittstelle implementiert und ein Objekt als Instanz dieser Klasse erstellt wird, verfügt das Objekt über eine Lebensdauer in der Anwendung, in der es ausgeführt wird.  Weitere Informationen finden Sie in [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) unter "Lebensdauer".  
  
## Beispiel  
 Im folgenden Beispiel wird mit der `Interface`\-Anweisung die Schnittstelle `thisInterface` definiert, die mit einer `Property`\-Anweisung und einer `Function`\-Anweisung implementiert werden muss.  
  
 [!code-vb[VbVbalrStatements#40](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_2.vb)]  
  
 Beachten Sie, dass die `Property`\-Anweisung und die `Function`\-Anweisung keine Blöcke in der Schnittstelle einführen, die mit `End Property` und `End Function` enden.  Die Schnittstelle definiert nur die Signatur ihrer Member.  Der vollständige `Property`\-Block und `Function`\-Block befinden sich in einer Klasse, die `thisInterface` implementiert.  
  
## Siehe auch  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)   
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Abweichungen bei generischen Schnittstellen](../Topic/Variance%20in%20Generic%20Interfaces%20\(C%23%20and%20Visual%20Basic\).md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)