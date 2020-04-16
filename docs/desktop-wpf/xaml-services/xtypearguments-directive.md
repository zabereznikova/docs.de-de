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
ms.openlocfilehash: 69da9329f140121b66c71d4cf2e99e9d14a1b207
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432629"
---
# <a name="xtypearguments-directive"></a>x:TypeArguments-Anweisung

Übergibt einschränkende Typargumente eines generischen Typs an den Konstruktor des generischen Typs.

## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|`object`|Eine Objektelementdeklaration eines XAML-Typs, die von einem generischen CLR-Typ unterstützt wird. Wenn `object` auf einen XAML-Typ verweist, der nicht aus `object` dem Standardmäßigen XAML-Namespace `object` stammt, ist ein Präfix erforderlich, um den XAML-Namespace anzugeben, wo vorhanden ist.|
|`typeString`|Eine Zeichenfolge, die einen oder mehrere XAML-Typnamen als Zeichenfolgen deklariert, die die Typargumente für den generischen CLR-Typ bereitstellt. Weitere Syntaxhinweise finden Sie unter Anmerkungen.|

## <a name="remarks"></a>Bemerkungen

In den meisten Fällen werden den XAML-Typen, `typeString` die als Informationselement in einer Zeichenfolge verwendet werden, vorangestellt. Typische Typen generischer CLR-Einschränkungen <xref:System.Int32> (z. B. und <xref:System.String>) stammen aus CLR-Basisklassenbibliotheken. Diese Bibliotheken sind nicht typischen frameworkspezifischen XAML-Standard-XAML-Namespaces zugeordnet und erfordern daher eine Präfixzuordnung für die XAML-Verwendung.

Sie können mehr als einen XAML-Typnamen angeben, indem Sie ein Kommatrennzeichen verwenden.

Wenn die generischen Einschränkungen selbst generische Typen verwenden, können die geschachtelten Einschränkungstypargumente in Klammern () enthalten sein.

Beachten Sie, `x:TypeArguments` dass diese Definition für .NET XAML-Dienste und die Verwendung von CLR-Unterstützung spezifisch ist. Eine Definition auf Sprachebene finden Sie in [ \[MS-XAML\] Abschnitt 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="usage-examples"></a>Anwendungsbeispiele

In diesen Beispielen wird davon ausgegangen, dass die folgenden XAML-Namespacedefinitionen deklariert werden:

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a>Listenzeichenfolge\<>

`<scg:List x:TypeArguments="sys:String" ...>`instanziiert ein <xref:System.Collections.Generic.List%601> neues <xref:System.String> mit einem Typargument.

### <a name="dictionarystringstring"></a>Wörterbuch-String,\<String->

`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`instanziiert ein <xref:System.Collections.Generic.Dictionary%602> neues <xref:System.String> mit zwei Typargumenten.

### <a name="queuekeyvaluepairstringstring"></a>Warteschlange<KeyValuePair\<String, String>>

`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`instanziiert eine <xref:System.Collections.Generic.Queue%601> neue, die <xref:System.Collections.Generic.KeyValuePair%602> eine Einschränkung von <xref:System.String> mit <xref:System.String>den inneren Einschränkungstypargumenten und hat.

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 und WPF Generische XAML-Verwendungen

Für die XAML 2006-Verwendung und XAML, die für WPF-Anwendungen verwendet wird, gelten die folgenden Einschränkungen für `x:TypeArguments` und generische Typverwendungen aus XAML im Allgemeinen:

- Nur das Stammelement einer XAML-Datei kann eine generische XAML-Verwendung unterstützen, die auf einen generischen Typ verweist.

- Das Root-Element muss einem generischen Typ mit mindestens einem Typargument zugeordnet werden. z. B. <xref:System.Windows.Navigation.PageFunction%601>. Die Seitenfunktionen sind das primäre Szenario für die allgemeine XAML-Nutzungsunterstützung in WPF.

- Das Stammelement XAML-Objektelement für das generische `x:Class`Element muss auch eine partielle Klasse mit deklarieren. Dies gilt auch dann, wenn Sie eine WPF-Buildaktion definieren.

- `x:TypeArguments`nicht auf geschachtelte generische Einschränkungen verweisen.

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 oder XAML 2006 ohne WPF 3.0 oder WPF 3.5 Abhängigkeit

In .NET XAML-Diensten für XAML 2006 oder XAML 2009 werden die WPF-bezogenen Einschränkungen für die generische XAML-Nutzung gelockert. Sie können ein generisches Objektelement an jeder beliebigen Position im XAML-Markup instanziieren, das das Sicherungstypsystem und das Objektmodell unterstützen können.

Wenn Sie XAML 2009 verwenden, anstatt die CLR-Basistypen zuzuordnen, um XAML-Typen für primitive Benutzerfürsprachen zu erhalten, `typeString`können Sie integrierte Typen für allgemeine [XAML-Sprachprimitive](types-for-primitives.md) als Informationselemente in einem verwenden. Sie können z. B. Folgendes deklarieren (Präfixzuordnungen werden nicht angezeigt, aber x ist der XAML-XAML-Namespace für XAML 2009):

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

In WPF und beim Targeting von .NET Framework 4 oder .NET Core 3.0 (oder `x:TypeArguments` höher) können Sie XAML 2009-Features zusammen mit, aber nur für loses XAML (XAML, das nicht markupkompiliert ist) verwenden. Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht. Wenn Sie die XAML-Kompilierung markieren müssen, müssen Sie unter den Einschränkungen arbeiten, die im Abschnitt [XAML 2006 und WPF Generic XAML Usages](#xaml-2006-and-wpf-generic-xaml-usages) angegeben sind. BAML wird nur in .NET Framework unterstützt.

## <a name="see-also"></a>Weitere Informationen

- [x:Class-Direktive](xclass-directive.md)
- [x:Type-Markuperweiterung](xtype-markup-extension.md)
- [Integrierte Typen für häufige XAML-Sprachprimitive](types-for-primitives.md)
- [Generics in XAML](generics.md)
