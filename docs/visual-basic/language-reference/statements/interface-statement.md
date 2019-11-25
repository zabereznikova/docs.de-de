---
title: Interface-Anweisung
ms.date: 05/12/2018
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: b606f24cf3baa13746834dfbf7ca6b9215fd3558
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348055"
---
# <a name="interface-statement-visual-basic"></a>Interface-Anweisung (Visual Basic)
Declares the name of an interface and introduces the definitions of the members that the interface comprises.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] _  
Interface name [ ( Of typelist ) ]  
    [ Inherits interfacenames ]  
    [ [ modifiers ] Property membername ]  
    [ [ modifiers ] Function membername ]  
    [ [ modifiers ] Sub membername ]  
    [ [ modifiers ] Event membername ]  
    [ [ modifiers ] Interface membername ]  
    [ [ modifiers ] Class membername ]  
    [ [ modifiers ] Structure membername ]  
End Interface  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`attributelist`|Dies ist optional. See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Dies ist optional. Einer der folgenden Werte ist möglich:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-  [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br/>- [Private Protected](../../language-reference/modifiers/private-protected.md)<br /><br /> Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Dies ist optional. See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`name`|Erforderlich. Name of this interface. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Dies ist optional. Specifies that this is a generic interface.|  
|`typelist`|Required if you use the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword. List of type parameters for this interface. Optionally, each type parameter can be declared variant by using `In` and `Out` generic modifiers. See [Type List](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Dies ist optional. Indicates that this interface inherits the attributes and members of another interface or interfaces. See [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`interfacenames`|Erforderlich, wenn Sie die `Inherits`-Anweisung verwenden. The names of the interfaces from which this interface derives.|  
|`modifiers`|Dies ist optional. Appropriate modifiers for the interface member being defined.|  
|`Property`|Dies ist optional. Defines a property that is a member of the interface.|  
|`Function`|Dies ist optional. Defines a `Function` procedure that is a member of the interface.|  
|`Sub`|Dies ist optional. Defines a `Sub` procedure that is a member of the interface.|  
|`Event`|Dies ist optional. Defines an event that is a member of the interface.|  
|`Interface`|Dies ist optional. Defines an interface that is a nested within this interface. The nested interface definition must terminate with an `End Interface` statement.|  
|`Class`|Dies ist optional. Defines a class that is a member of the interface. The member class definition must terminate with an `End Class` statement.|  
|`Structure`|Dies ist optional. Defines a structure that is a member of the interface. The member structure definition must terminate with an `End Structure` statement.|  
|`membername`|Required for each property, procedure, event, interface, class, or structure defined as a member of the interface. Der Name des Members.|  
|`End Interface`|Beendet die `Interface`-Definition.|  
  
## <a name="remarks"></a>Hinweise  
 An *interface* defines a set of members, such as properties and procedures, that classes and structures can implement. The interface defines only the signatures of the members and not their internal workings.  
  
 A class or structure implements the interface by supplying code for every member defined by the interface. Finally, when the application creates an instance from that class or structure, an object exists and runs in memory. For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) and [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 `Interface` kann nur auf Namespace- oder Modulebene verwendet werden. This means the *declaration context* for an interface must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure or block. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Interfaces default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regeln  
  
- **Nesting Interfaces.** You can define one interface within another. The outer interface is called the *containing interface*, and the inner interface is called a *nested interface*.  
  
- **Member Declaration.** When you declare a property or procedure as a member of an interface, you are defining only the *signature* of that property or procedure. This includes the element type (property or procedure), its parameters and parameter types, and its return type. Because of this, the member definition uses only one line of code, and terminating statements such as `End Function` or `End Property` are not valid in an interface.  
  
     In contrast, when you define an enumeration or structure, or a nested class or interface, it is necessary to include their data members.  
  
- **Member Modifiers.** You cannot use any access modifiers when defining module members, nor can you specify [Shared](../../../visual-basic/language-reference/modifiers/shared.md) or any procedure modifier except [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md). You can declare any member with [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md), and you can use [Default](../../../visual-basic/language-reference/modifiers/default.md) when defining a property, as well as [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) or [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
- **Vererbung.** If the interface uses the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md), you can specify one or more base interfaces. You can inherit from two interfaces even if they each define a member with the same name. If you do so, the implementing code must use name qualification to specify which member it is implementing.  
  
     An interface cannot inherit from another interface with a more restrictive access level. For example, a `Public` interface cannot inherit from a `Friend` interface.  
  
     An interface cannot inherit from an interface nested within it.  
  
- **Implementation.** When a class uses the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) statement to implement this interface, it must implement every member defined within the interface. Furthermore, each signature in the implementing code must exactly match the corresponding signature defined in this interface. However, the name of the member in the implementing code does not have to match the member name as defined in the interface.  
  
     When a class is implementing a procedure, it cannot designate the procedure as `Shared`.  
  
- **Default Property.** An interface can specify at most one property as its *default property*, which can be referenced without using the property name. You specify such a property by declaring it with the [Default](../../../visual-basic/language-reference/modifiers/default.md) modifier.  
  
     Notice that this means that an interface can define a default property only if it inherits none.  
  
## <a name="behavior"></a>Verhalten  
  
- **Access Level.** All interface members implicitly have [Public](../../../visual-basic/language-reference/modifiers/public.md) access. You cannot use any access modifier when defining a member. However, a class implementing the interface can declare an access level for each implemented member.  
  
     If you assign a class instance to a variable, the access level of its members can depend on whether the data type of the variable is the underlying interface or the implementing class. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
     [!code-vb[VbVbalrStatements#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#39)]  
  
     If you access class members through `varAsInterface`, they all have public access. However, if you access members through `varAsClass`, the `Sub` procedure `doSomething` has private access.  
  
- **Scope.** An interface is in scope throughout its namespace, class, structure, or module.  
  
     The scope of every interface member is the entire interface.  
  
- **Lifetime.** An interface does not itself have a lifetime, nor do its members. When a class implements an interface and an object is created as an instance of that class, the object has a lifetime within the application in which it is running. For more information, see "Lifetime" in [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md).  
  
## <a name="example"></a>Beispiel  
 The following example uses the `Interface` statement to define an interface named `thisInterface`, which must be implemented with a `Property` statement and a `Function` statement.  
  
 [!code-vb[VbVbalrStatements#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#40)]  
  
 Note that the `Property` and `Function` statements do not introduce blocks ending with `End Property` and `End Function` within the interface. The interface defines only the signatures of its members. The full `Property` and `Function` blocks appear in a class that implements `thisInterface`.  
  
## <a name="see-also"></a>Siehe auch

- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)
- [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)
- [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Varianz in generischen Schnittstellen](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
