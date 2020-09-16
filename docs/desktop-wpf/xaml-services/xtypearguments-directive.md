---
title: x:TypeArguments-Anweisung
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 430ab65af52282ccb1d429cd2523efe213f13609
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543550"
---
# <a name="xtypearguments-directive"></a>x:TypeArguments-Anweisung

Übergibt einschränkende Typargumente eines generischen an den Konstruktor des generischen Typs.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|`object`|Eine Objekt Element Deklaration eines XAML-Typs, der durch einen generischen CLR-Typ unterstützt wird. Wenn `object` auf einen XAML-Typ verweist, der nicht aus dem XAML-Standard Namespace gehört, `object` erfordert ein Präfix, um den XAML-Namespace anzugeben, in dem `object` vorhanden ist.|
|`typeString`|Eine Zeichenfolge, die einen oder mehrere XAML-Typnamen als Zeichen folgen deklariert, die die Typargumente für den generischen CLR-Typ bereitstellt. Weitere Informationen zur Syntax finden Sie in den hinweisen.|

## <a name="remarks"></a>Hinweise

In den meisten Fällen werden die XAML-Typen, die als Informationselement in einer Zeichenfolge verwendet werden, als `typeString` Präfix vorangestellt. Typische Typen von generischen CLR-Einschränkungen (z. b. <xref:System.Int32> und <xref:System.String> ) stammen aus CLR-Basisklassen Bibliotheken. Diese Bibliotheken sind nicht typischen Framework-spezifischen XAML-Standard Namespaces zugeordnet und erfordern daher eine Präfix Zuordnung für die XAML-Verwendung.

Sie können mehr als einen XAML-Typnamen angeben, indem Sie ein Komma Trennzeichen verwenden.

Wenn die generischen Einschränkungen selbst generische Typen verwenden, können die Argumente der geschachtelten Einschränkungs Typen in Klammern () enthalten sein.

Beachten Sie, dass diese Definition von `x:TypeArguments` speziell für .net XAML-Dienste und die Verwendung von CLR-Unterstützung gilt. Eine Definition auf Sprachebene finden Sie im [ \[ \] Abschnitt 5.3.11 des MS-XAML-Abschnitts](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="usage-examples"></a>Anwendungsbeispiele

Nehmen Sie für diese Beispiele an, dass die folgenden XAML-Namespace Definitionen deklariert sind:

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a>List\<String>

`<scg:List x:TypeArguments="sys:String" ...>` instanziiert ein neues- <xref:System.Collections.Generic.List%601> Argument mit einem <xref:System.String> Typargument.

### <a name="dictionarystringstring"></a>Wörterbuch\<String,String>

`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instanziiert eine neue <xref:System.Collections.Generic.Dictionary%602> mit zwei <xref:System.String> Typargumenten.

### <a name="queuekeyvaluepairstringstring"></a>Queue<KeyValuePair\<String,String>>

`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instanziiert einen neuen <xref:System.Collections.Generic.Queue%601> , der über eine Einschränkung von <xref:System.Collections.Generic.KeyValuePair%602> mit den inneren Einschränkungs Typargumenten <xref:System.String> und verfügt <xref:System.String> .

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 und allgemeine WPF-XAML-Verwendungen

Bei der Verwendung von XAML 2006 und XAML, die für WPF-Anwendungen verwendet werden, gibt es die folgenden Einschränkungen für `x:TypeArguments` und generische typverwendungen von XAML im allgemeinen:

- Nur das Stamm Element einer XAML-Datei kann eine generische XAML-Verwendung unterstützen, die auf einen generischen Typ verweist.

- Das root-Element muss einem generischen Typ mit mindestens einem Typargument zugeordnet werden. z. B. <xref:System.Windows.Navigation.PageFunction%601>. Die Seitenfunktionen sind das primäre Szenario für die generische Verwendung von XAML in WPF.

- Das Stamm Element-XAML-Objekt Element für den generischen muss ebenfalls mithilfe von eine partielle Klasse deklarieren `x:Class` . Dies gilt auch, wenn Sie eine WPF-Buildaktion definieren.

- `x:TypeArguments` auf die generischen generischen Einschränkungen kann nicht verwiesen werden.

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 oder XAML 2006 ohne WPF 3,0 oder WPF 3,5-Abhängigkeit

In .net XAML-Diensten für XAML 2006 oder XAML 2009 werden die WPF-bezogenen Einschränkungen bei der generischen XAML-Verwendung gelockert. Sie können ein generisches Objekt Element an einer beliebigen Position in XAML-Markup instanziieren, die das Unterstützungs-Typsystem und das Objektmodell unterstützen können.

Wenn Sie XAML 2009 anstelle der Zuordnung der CLR-Basis Typen zum Abrufen von XAML-Typen für allgemeine sprach primitive verwenden, können Sie [integrierte Typen für allgemeine XAML-sprach primitive](types-for-primitives.md) als Informationselemente in einem verwenden `typeString` . Sie könnten z. b. Folgendes deklarieren (Präfix Zuordnungen werden nicht angezeigt, aber x ist der XAML-sprach Namespace XAML-Namespace für XAML 2009):

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

In WPF und beim Ziel .NET Framework 4 oder .net Core 3,0 (oder höher) können Sie XAML 2009-Funktionen zusammen mit verwenden, `x:TypeArguments` aber nur für Loose XAML (XAML, das nicht Markup kompiliert ist). Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht. Wenn Sie das XAML-Markup kompilieren müssen, müssen Sie unter den im Abschnitt [generische XAML-Verwendungen von XAML 2006 und WPF](#xaml-2006-and-wpf-generic-xaml-usages) notierten Einschränkungen arbeiten. BAML wird nur in .NET Framework unterstützt.

## <a name="see-also"></a>Siehe auch

- [x:Class-Direktive](xclass-directive.md)
- [x:Type-Markuperweiterung](xtype-markup-extension.md)
- [Integrierte Typen für häufige XAML-Sprachprimitive](types-for-primitives.md)
- [Generics in XAML](generics.md)
