---
title: AttributeUsage (C#)
ms.date: 04/25/2018
ms.openlocfilehash: a3a82e33d7259ec56ec3e907bc3d4d9f8a01167d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "61668717"
---
# <a name="attributeusage-c"></a>AttributeUsage (C#)

Bestimmt, wie eine benutzerdefinierte Attributklasse verwendet werden kann. Bei <xref:System.AttributeUsageAttribute> handelt es sich um ein Attribut, das Sie auf benutzerdefinierte Attributdefinitionen anwenden. Mithilfe des `AttributeUsage`-Attribut können Sie Folgendes steuern:

- Auf welche Programmelemente das Attribut angewendet werden kann. Wenn Sie dessen Verwendung nicht einschränken, kann ein Attribut auf jedes der folgenden Programmelemente angewendet werden:
  - Assembly
  - module
  - -Feld
  - event
  - Methode
  - Parameter
  - Eigenschaft
  - return
  - Typ
- Ob ein Attribut mehrfach auf ein einzelnes Programmelement angewendet werden kann.
- Ob Attribute von abgeleiteten Klassen geerbt werden.

Die Standardeinstellungen ähneln folgendem Beispiel, wenn Sie explizit angewendet werden:

[!code-csharp[Define a new attribute](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#1)]

In diesem Beispiel kann die `NewAttribute`-Klasse auf jedes unterstützte Programmelement angewendet werden. Es kann jedoch nur einmal auf jede Entität angewendet werden. Wenn das Attribut auf eine Basisklasse angewendet wird, wird es an eine abgeleitete Klasse vererbt.

Die Argumente <xref:System.AttributeUsageAttribute.AllowMultiple> und <xref:System.AttributeUsageAttribute.Inherited> sind optional, sodass folgender Code die gleiche Wirkung hat:

[!code-csharp[Omit optional attributes](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#2)]

Das erste <xref:System.AttributeUsageAttribute>-Argument muss mindestens ein Element der <xref:System.AttributeTargets>-Enumeration sein. Mehrere Zieltypen können wie im folgenden Beispiel dargestellt mithilfe des OR-Operators verknüpft werden:

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#1)]

Ab C# 7.3 können Attribut auf das Eigenschaften- oder das Unterstützungsfeld einer automatisch implementierten Eigenschaft angewendet werden. Das Attribut wird auf die Eigenschaft angewendet, sofern Sie den `field`-Bezeichner des Attributs nicht angeben. Beides wird im folgenden Beispiel veranschaulicht:

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#2)]

Wenn das <xref:System.AttributeUsageAttribute.AllowMultiple>-Argument auf `true` festgelegt ist, kann das daraus entstehende Attribut wie im folgenden Beispiel dargestellt mehr als einmal auf eine einzelne Entität angewendet werden:

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/MultiUseAttribute.cs#1)]

In diesem Fall kann `MultiUseAttribute` wiederholt angewendet werden, da `AllowMultiple` auf `true` festgelegt wurde. Beide gezeigten Formate für das Anwenden von mehreren Attributen sind gültig.

Wenn <xref:System.AttributeUsageAttribute.Inherited> auf `false` festgelegt wurde, wird das Attribut nicht von Klassen geerbt, die von einer Attributklasse abgeleitet werden. Beispiel:

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/NonInheritedAttribute.cs#1)]

In diesem Fall wird `NonInheritedAttribute` nicht durch Vererbung auf `DClass` angewendet.

## <a name="remarks"></a>Hinweise

Das `AttributeUsage`-Attribut ist für die einmalige Nutzung bestimmt. Es kann nicht mehr als einmal auf dieselbe Klasse angewendet werden. `AttributeUsage` ist ein Alias für <xref:System.AttributeUsageAttribute>.

Weitere Informationen finden Sie unter [Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))](accessing-attributes-by-using-reflection.md).

## <a name="example"></a>Beispiel

In folgendem Beispiel wird die Wirkung der Argumente <xref:System.AttributeUsageAttribute.Inherited> und <xref:System.AttributeUsageAttribute.AllowMultiple> auf das Attribut <xref:System.AttributeUsageAttribute> und die Enumeration benutzerdefinierter Attribute veranschaulicht, die auf eine Klasse angewendet wurden.

[!code-csharp[Applying and querying attributes](../../../../../samples/snippets/csharp/attributes/Program.cs#1)]

## <a name="sample-output"></a>Beispielausgabe

```text
Attributes on Base Class:
FirstAttribute
SecondAttribute
Attributes on Derived Class:
ThirdAttribute
ThirdAttribute
SecondAttribute
```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Attribute>
- <xref:System.Reflection>
- [C#-Programmierhandbuch](../..//index.md)
- [Attribute](../../../..//standard/attributes/index.md)
- [Reflektion (C#)](../reflection.md)
- [Attribute](index.md)
- [Erstellen benutzerdefinierter Attribute (C#)](creating-custom-attributes.md)
- [Zugriff auf Attribute mit Reflektion (C#)](accessing-attributes-by-using-reflection.md)
