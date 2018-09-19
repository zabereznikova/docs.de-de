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
ms.openlocfilehash: 28eda94914125f2c5849a471671c8e283475c82c
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46321391"
---
# <a name="xtypearguments-directive"></a>x:TypeArguments-Anweisung
Einschränken von übergibt Typargumente eines generischen an den Konstruktor des generischen Typs.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`object`|Ein Object-Element-Deklaration eines XAML-Typs, der von einem generischen CLR-Typ unterstützt wird. Wenn `object` verweist auf einen XAML-Typ, der nicht aus dem XAML-Standardnamespace ist `object` erfordert ein Präfix an, dass der XAML-Namespace, in denen `object` vorhanden ist.|  
|`typeString`|Eine Zeichenfolge, die eine oder mehrere XAML deklariert Typnamen als Zeichenfolgen, die die Typargumente für den generischen CLR-Typ. Anmerkungen zu dieser Version zusätzliche Syntax finden Sie unter "Hinweise".|  
  
## <a name="remarks"></a>Hinweise  
 In den meisten Fällen, die XAML-Typen, die verwendet werden, als ein Informationselement in einem `typeString` Zeichenfolge vorangestellt werden. Typische Typen von CLR generische Einschränkungen (z. B. <xref:System.Int32> und <xref:System.String>) stammen aus CLR-Basisklassenbibliotheken. Diese Bibliotheken sind nicht zugeordneten typischen frameworkspezifische-standardmäßigen XAML-Namespaces und erfordert daher eine Präfix-Zuordnung für die Verwendung von XAML.  
  
 Sie können mehr als eine XAML-Typnamen angeben, durch ein Komma als Trennzeichen verwenden.  
  
 Wenn der generischen Einschränkungen selbst generische Typen verwenden, können die geschachtelte Einschränkung Typargumente durch Klammern () enthalten sein.  
  
 Beachten Sie, dass diese Definition von `x:TypeArguments` bezieht sich auf .NET Framework-XAML-Dienste, und Verwenden von CLR-Unterstützung. Eine Definition auf Sprachebene finden Sie im [ \[MS-XAML-\] Abschnitt 5.3.11](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="usage-examples"></a>Beispiele zur Verwendung  
 Diesen Beispielen wird davon ausgegangen Sie, dass die folgenden XAML-Namespacedefinitionen deklariert werden:  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a>Liste\<Zeichenfolge >  
 `<scg:List x:TypeArguments="sys:String" ...>` instanziiert ein neues <xref:System.Collections.Generic.List%601> mit einem <xref:System.String> Typargument.  
  
### <a name="dictionarystringstring"></a>Wörterbuch\<Zeichenfolge, Zeichenfolge >  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instanziiert ein neues <xref:System.Collections.Generic.Dictionary%602> mit zwei <xref:System.String> Typargumente.  
  
### <a name="queuekeyvaluepairstringstring"></a>Warteschlange < KeyValuePair\<String, String >>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instanziiert ein neues <xref:System.Collections.Generic.Queue%601> enthält, die die Einschränkung der <xref:System.Collections.Generic.KeyValuePair%602> mit die Typargumente für die interne Einschränkung <xref:System.String> und <xref:System.String>.  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>Generische XAML-Verwendungen von XAML 2006 und WPF  
 Für die Verwendung von XAML 2006 und XAML, das für WPF-Anwendungen verwendet wird, der die folgenden Einschränkungen gelten für `x:TypeArguments` und generische Typverwendungen aus XAML im Allgemeinen:  
  
-   Nur das Stammelement einer XAML-Datei kann es sich um einen generischen XAML-Verwendung unterstützen, die einen generischen Typ verweist.  
  
-   Das Stammelement muss auf einen generischen Typ mit mindestens einem Typargument zugeordnet. Ein Beispiel hierfür ist <xref:System.Windows.Navigation.PageFunction%601>. Die Seitenfunktionen sind das primäre Szenario für die generischen Verwendung-Unterstützung in WPF-XAML.  
  
-   Außerdem muss das Stammelement Element XAML-Objektelement für das generische deklariert eine partielle Klasse mit `x:Class`. Dies gilt auch, wenn Definieren eines WPF-Buildvorgang.  
  
-   `x:TypeArguments` Geschachtelte generische Einschränkungen kann nicht verwiesen werden.  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 oder XAML 2006 ohne WPF 3.0 oder WPF 3.5 Abhängigkeit  
 In .NET Framework-XAML-Dienste für XAML 2006 oder XAML 2009 sind die WPF-bezogene Einschränkungen für generische XAML-Verwendung gelockert. Sie können ein generisches Objektelement an einer beliebigen Position im XAML-Markup instanziieren, die das dahinter liegende Typ und dem Objektmodell unterstützen kann.  
  
 Wenn Sie XAML 2009 verwenden anstelle von mapping des CLR-Basistypen zum Abrufen von XAML-Typen für häufige Sprachprimitive, können Sie [integrierte Typen für häufige XAML-Sprachprimitive](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) als Informationselemente in eine `typeString`. Sie können z. B. die folgenden deklarieren (Präfix-Zuordnungen, die nicht angezeigt, aber x ist der XAML-Sprachnamespace XAML für XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 In WPF und Zielgruppenadressierung [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], können Sie XAML 2009-Funktionen zusammen mit `x:TypeArguments` jedoch nur für loose XAML (XAML, das nicht markupkompiliert ist). Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht. Wenn Sie in Markup der XAML kompilieren müssen, müssen Sie unter den Einschränkungen, die im Abschnitt "XAML 2006 und WPF-generische XAML-Verwendungen" erwähnt ausgeführt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [x:Class-Anweisung](../../../docs/framework/xaml-services/x-class-directive.md)  
 [x:Type-Markuperweiterung](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [Integrierte Typen für häufige XAML-Sprachprimitive](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)  
 [Generika in XAML](../../../docs/framework/xaml-services/generics-in-xaml.md)
