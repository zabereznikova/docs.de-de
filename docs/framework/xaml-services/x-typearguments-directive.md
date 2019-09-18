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
ms.openlocfilehash: a2a960870d368e57272b3368e69eb38ebbe2ba5d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053715"
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
 In den meisten Fällen werden die XAML-Typen, die als Informationselement in einer `typeString` Zeichenfolge verwendet werden, als Präfix vorangestellt. Typische Typen von generischen CLR <xref:System.Int32> -Einschränkungen (z. b. und <xref:System.String>) stammen aus CLR-Basisklassen Bibliotheken. Diese Bibliotheken sind nicht typischen Framework-spezifischen XAML-Standard Namespaces zugeordnet und erfordern daher eine Präfix Zuordnung für die XAML-Verwendung.  
  
 Sie können mehr als einen XAML-Typnamen angeben, indem Sie ein Komma Trennzeichen verwenden.  
  
 Wenn die generischen Einschränkungen selbst generische Typen verwenden, können die Argumente der geschachtelten Einschränkungs Typen in Klammern () enthalten sein.  
  
 Beachten Sie, dass diese `x:TypeArguments` Definition von für .NET Framework XAML-Dienste und die Verwendung von CLR-Unterstützung spezifisch ist. Eine Definition auf Sprachebene finden Sie im [ \[Abschnitt 5.3.11 des MS-XAML\] -Abschnitts](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="usage-examples"></a>Verwendungs Beispiele  
 Nehmen Sie für diese Beispiele an, dass die folgenden XAML-Namespace Definitionen deklariert sind:  
  
```xaml  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a>Listen\<Zeichenfolge >  
 `<scg:List x:TypeArguments="sys:String" ...>`instanziiert ein neues <xref:System.Collections.Generic.List%601> -Argument <xref:System.String> mit einem Typargument.  
  
### <a name="dictionarystringstring"></a>Wörter\<Buch Zeichenfolge, String >  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`instanziiert eine neue <xref:System.Collections.Generic.Dictionary%602> mit zwei <xref:System.String> Typargumenten.  
  
### <a name="queuekeyvaluepairstringstring"></a>Queue<KeyValuePair\<String,String>>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`instanziiert einen neuen <xref:System.Collections.Generic.Queue%601> , der über eine Einschränkung <xref:System.Collections.Generic.KeyValuePair%602> von mit den inneren Einschränkungs <xref:System.String> Typargumenten und <xref:System.String>verfügt.  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 und allgemeine WPF-XAML-Verwendungen  
 Bei der Verwendung von XAML 2006 und XAML, die für WPF-Anwendungen verwendet werden, gibt es `x:TypeArguments` die folgenden Einschränkungen für und generische typverwendungen von XAML im allgemeinen:  
  
- Nur das Stamm Element einer XAML-Datei kann eine generische XAML-Verwendung unterstützen, die auf einen generischen Typ verweist.  
  
- Das root-Element muss einem generischen Typ mit mindestens einem Typargument zugeordnet werden. Ein Beispiel hierfür <xref:System.Windows.Navigation.PageFunction%601>ist. Die Seitenfunktionen sind das primäre Szenario für die generische Verwendung von XAML in WPF.  
  
- Das Stamm Element-XAML-Objekt Element für den generischen muss ebenfalls mithilfe `x:Class`von eine partielle Klasse deklarieren. Dies gilt auch, wenn Sie eine WPF-Buildaktion definieren.  
  
- `x:TypeArguments`auf die generischen generischen Einschränkungen kann nicht verwiesen werden.  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 oder XAML 2006 ohne WPF 3,0 oder WPF 3,5-Abhängigkeit  
 In .NET Framework XAML-Dienste für XAML 2006 oder XAML 2009 werden die WPF-bezogenen Einschränkungen bei der generischen XAML-Verwendung gelockert. Sie können ein generisches Objekt Element an einer beliebigen Position in XAML-Markup instanziieren, die das Unterstützungs-Typsystem und das Objektmodell unterstützen können.  
  
 Wenn Sie XAML 2009 anstelle der Zuordnung der CLR-Basis Typen zum Abrufen von XAML-Typen für allgemeine sprach primitive verwenden, können Sie [integrierte Typen für allgemeine XAML-sprach primitive](built-in-types-for-common-xaml-language-primitives.md) als Informationselemente in einem `typeString`verwenden. Sie könnten z. b. Folgendes deklarieren (Präfix Zuordnungen werden nicht angezeigt, aber x ist der XAML-sprach Namespace XAML-Namespace für XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 In WPF und beim Ziel .NET Framework 4 können Sie XAML 2009-Funktionen zusammen mit `x:TypeArguments` verwenden, aber nur für Loose XAML (XAML, das nicht Markup kompiliert ist). Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht. Wenn Sie das XAML-Markup kompilieren müssen, müssen Sie unter den im Abschnitt "generische XAML-Verwendungen von XAML 2006 und WPF" notierten Einschränkungen arbeiten.  
  
## <a name="see-also"></a>Siehe auch

- [x:Class-Anweisung](x-class-directive.md)
- [x:Type-Markuperweiterung](x-type-markup-extension.md)
- [Integrierte Typen für häufige XAML-Sprachprimitive](built-in-types-for-common-xaml-language-primitives.md)
- [Generics in XAML](generics-in-xaml.md)
