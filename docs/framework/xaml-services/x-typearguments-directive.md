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
ms.openlocfilehash: 2e64c716ee85934bf02c016ee408b8e5f612a819
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837193"
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
|`object`|Eine Objekt Element Deklaration eines XAML-Typs, der durch einen generischen CLR-Typ unterstützt wird. Wenn `object` auf einen XAML-Typ verweist, der nicht aus dem XAML-Standard Namespace besteht, erfordert `object` ein Präfix, um den XAML-Namespace anzugeben, in dem `object` vorhanden ist.|  
|`typeString`|Eine Zeichenfolge, die einen oder mehrere XAML-Typnamen als Zeichen folgen deklariert, die die Typargumente für den generischen CLR-Typ bereitstellt. Weitere Informationen zur Syntax finden Sie in den hinweisen.|  
  
## <a name="remarks"></a>Hinweise  
 In den meisten Fällen werden die XAML-Typen, die in einer `typeString` Zeichenfolge als Informationselement verwendet werden, als Präfix vorangestellt. Typische Typen von generischen CLR-Einschränkungen (z. b. <xref:System.Int32> und <xref:System.String>) stammen aus CLR-Basisklassen Bibliotheken. Diese Bibliotheken sind nicht typischen Framework-spezifischen XAML-Standard Namespaces zugeordnet und erfordern daher eine Präfix Zuordnung für die XAML-Verwendung.  
  
 Sie können mehr als einen XAML-Typnamen angeben, indem Sie ein Komma Trennzeichen verwenden.  
  
 Wenn die generischen Einschränkungen selbst generische Typen verwenden, können die Argumente der geschachtelten Einschränkungs Typen in Klammern () enthalten sein.  
  
 Beachten Sie, dass diese Definition von `x:TypeArguments` für .NET Framework XAML-Dienste und die Verwendung von CLR-Unterstützung spezifisch ist. Eine Definition auf Sprachebene finden Sie in [\[MS-XAML\] Abschnitt 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
## <a name="usage-examples"></a>Anwendungsbeispiele  
 Nehmen Sie für diese Beispiele an, dass die folgenden XAML-Namespace Definitionen deklariert sind:  
  
```xaml  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a>Liste\<Zeichenfolge >  
 `<scg:List x:TypeArguments="sys:String" ...>` instanziiert eine neue <xref:System.Collections.Generic.List%601> mit einem <xref:System.String> Typargument.  
  
### <a name="dictionarystringstring"></a>Wörterbuch\<Zeichenfolge, Zeichenfolge >  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instanziiert eine neue <xref:System.Collections.Generic.Dictionary%602> mit zwei <xref:System.String> Typargumenten.  
  
### <a name="queuekeyvaluepairstringstring"></a>Queue<KeyValuePair\<String,String>>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instanziiert ein neues <xref:System.Collections.Generic.Queue%601>, das über eine Einschränkung von <xref:System.Collections.Generic.KeyValuePair%602> mit den inneren Einschränkungs Typargumenten <xref:System.String> und <xref:System.String>verfügt.  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 und allgemeine WPF-XAML-Verwendungen  
 Bei der Verwendung von XAML 2006 und XAML, die für WPF-Anwendungen verwendet werden, gibt es die folgenden Einschränkungen für `x:TypeArguments` und generische typverwendungen von XAML im allgemeinen:  
  
- Nur das Stamm Element einer XAML-Datei kann eine generische XAML-Verwendung unterstützen, die auf einen generischen Typ verweist.  
  
- Das root-Element muss einem generischen Typ mit mindestens einem Typargument zugeordnet werden. z. B. <xref:System.Windows.Navigation.PageFunction%601>. Die Seitenfunktionen sind das primäre Szenario für die generische Verwendung von XAML in WPF.  
  
- Das Stamm Element-XAML-Objekt Element für das generische muss auch eine partielle Klasse mit `x:Class`deklarieren. Dies gilt auch, wenn Sie eine WPF-Buildaktion definieren.  
  
- `x:TypeArguments` kann nicht auf die generischen generischen Einschränkungen verweisen.  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 oder XAML 2006 ohne WPF 3,0 oder WPF 3,5-Abhängigkeit  
 In .NET Framework XAML-Dienste für XAML 2006 oder XAML 2009 werden die WPF-bezogenen Einschränkungen bei der generischen XAML-Verwendung gelockert. Sie können ein generisches Objekt Element an einer beliebigen Position in XAML-Markup instanziieren, die das Unterstützungs-Typsystem und das Objektmodell unterstützen können.  
  
 Wenn Sie XAML 2009 anstelle der Zuordnung der CLR-Basis Typen zum Abrufen von XAML-Typen für allgemeine sprach primitive verwenden, können Sie [integrierte Typen für allgemeine XAML-sprach primitive](built-in-types-for-common-xaml-language-primitives.md) als Informationselemente in einem `typeString`verwenden. Sie könnten z. b. Folgendes deklarieren (Präfix Zuordnungen werden nicht angezeigt, aber x ist der XAML-sprach Namespace XAML-Namespace für XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 In WPF und beim Ziel .NET Framework 4 können Sie XAML 2009-Funktionen zusammen mit `x:TypeArguments` verwenden, jedoch nur für Loose XAML (XAML, das nicht Markup kompiliert ist). Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht. Wenn Sie das XAML-Markup kompilieren müssen, müssen Sie unter den im Abschnitt "generische XAML-Verwendungen von XAML 2006 und WPF" notierten Einschränkungen arbeiten.  
  
## <a name="see-also"></a>Siehe auch

- [x:Class-Anweisung](x-class-directive.md)
- [x:Type-Markuperweiterung](x-type-markup-extension.md)
- [Integrierte Typen für häufige XAML-Sprachprimitive](built-in-types-for-common-xaml-language-primitives.md)
- [Generics in XAML](generics-in-xaml.md)
