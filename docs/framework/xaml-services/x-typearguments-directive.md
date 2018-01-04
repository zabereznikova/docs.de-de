---
title: x:TypeArguments-Anweisung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
caps.latest.revision: "18"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e601fb5895460e52aa21836c542d0b1367527f09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="xtypearguments-directive"></a>x:TypeArguments-Anweisung
Einschränken übergibt die Typargumente einer generischen an den Konstruktor des generischen Typs.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`object`|Ein Objektelementdeklaration eines XAML-Typs, der durch einen generischen CLR-Typ unterstützt wird. Wenn `object` bezieht sich auf einen XAML-Typ, der nicht aus dem XAML-Standardnamespace ist `object` erfordert ein Präfix an, dass die Verwendung von XAML-Namespace, in dem `object` vorhanden ist.|  
|`typeString`|Eine Zeichenfolge, die eine oder mehrere XAML deklariert-Typnamen Zeichenfolgen, die die Typargumente für den generischen CLR-Typ. Zusätzliche Syntaxhinweise finden Sie unter "Hinweise".|  
  
## <a name="remarks"></a>Hinweise  
 In den meisten Fällen, die XAML-Typen, die verwendet werden, als ein Informationselement in einem `typeString` Zeichenfolge vorangestellt werden. Typische generische Einschränkungen CLR-Typen (z. B. <xref:System.Int32> und <xref:System.String>) aus CLR-Basisklassenbibliotheken stammen. Diese Bibliotheken sind nicht zugeordnete typischen Framework-spezifischen XAML-Standardnamespaces und erfordert daher eine/Präfix-Zuordnung für die Verwendung von XAML-Verwendung.  
  
 Sie können mehr als eine XAML-Typnamen angeben, durch ein Komma als Trennzeichen verwenden.  
  
 Wenn der generischen Einschränkungen selbst generische Typen zu verwenden, können die geschachtelten Einschränkung Typargumente durch Klammern () enthalten sein.  
  
 Beachten Sie, dass diese Definition von `x:TypeArguments` bezieht sich auf .NET Framework-XAML-Dienste, und Verwenden von CLR-Unterstützung. Eine Definition auf Sprachebene finden Sie im [ \[MS-XAML-\] Abschnitt 5.3.11](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="usage-examples"></a>Anwendungsbeispiele  
 Für diesen Beispielen wird davon ausgegangen Sie, dass die folgenden XAML-Namespacedefinitionen deklariert werden:  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a>Liste\<Zeichenfolge >  
 `<scg:List x:TypeArguments="sys:String" ...>`instanziiert eine neue <xref:System.Collections.Generic.List%601> mit einem <xref:System.String> Typargument.  
  
### <a name="dictionarystringstring"></a>Wörterbuch\<Zeichenfolge, Zeichenfolge >  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`instanziiert eine neue <xref:System.Collections.Generic.Dictionary%602> mit zwei <xref:System.String> Typargumente.  
  
### <a name="queuekeyvaluepairstringstring"></a>Warteschlange < KeyValuePair\<Zeichenfolge "," String ">>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`instanziiert eine neue <xref:System.Collections.Generic.Queue%601> enthält, die die Einschränkung der <xref:System.Collections.Generic.KeyValuePair%602> mit die Typargumente für die interne Einschränkung <xref:System.String> und <xref:System.String>.  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 und WPF generische XAML-Verwendungen  
 Für die Verwendung von XAML 2006 und XAML, das für die WPF-Anwendungen verwendet wird, der die folgenden Einschränkungen gelten für `x:TypeArguments` und generischen Typs Verwendungen von XAML im Allgemeinen:  
  
-   Nur das Stammelement einer XAML-Datei kann es sich um eine allgemeine XAML-Verwendung unterstützen, die einen generischen Typ verweist.  
  
-   Das Stammelement muss ein generischer Typ mit mindestens einem Typargument zuordnen. Ein Beispiel ist <xref:System.Windows.Navigation.PageFunction%601>. Die Seitenfunktionen sind das Hauptszenario für die Verwendung von XAML-generischen Verwendung-Unterstützung in WPF.  
  
-   Außerdem muss der Stamm-XAML-Objektelement für den generischen deklariert eine partielle Klasse mit `x:Class`. Dies gilt auch, wenn Definieren eines WPF-Buildvorgang.  
  
-   `x:TypeArguments`Geschachtelte generische Einschränkungen kann nicht verwiesen werden.  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 oder XAML 2006 ohne WPF 3.0 oder WPF 3.5 Abhängigkeit  
 In .NET Framework-XAML-Dienste für XAML 2006 oder XAML 2009 werden die WPF-bezogene Einschränkungen für generische XAML-Verwendung gelockert. Sie können ein generisches Objektelement an einer beliebigen Position im XAML-Markup instanziieren, die die dahinter liegende Typ und dem Objektmodell unterstützen kann.  
  
 Bei Verwendung von XAML 2009 anstelle von mapping des CLR-Basistypen um XAML-Typen für häufige Sprachprimitive zu erhalten, können Sie [integrierte Typen für häufige XAML-Sprachprimitive](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) als Informationselementen in einem `typeString`. Beispielsweise konnten Sie die folgenden deklarieren (/ Präfix-Zuordnungen, die nicht angezeigt, aber x ist die Verwendung von XAML-Verwendung von XAML-Sprachnamespace für XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 In WPF und beim Abzielen auf [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], können Sie XAML 2009-Funktionen zusammen mit `x:TypeArguments` jedoch nur für loose XAML (, das nicht markupkompiliert ist). Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht. Wenn Sie Markup den XAML-Code kompilieren müssen, müssen Sie unter den Einschränkungen dar, die im Abschnitt "XAML 2006 und WPF generische XAML-Verwendungen" ausgeführt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [x:Class-Anweisung](../../../docs/framework/xaml-services/x-class-directive.md)  
 [x:Type-Markuperweiterung](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [Integrierte Typen für häufige XAML-Sprachprimitive](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)  
 [Generika in XAML](../../../docs/framework/xaml-services/generics-in-xaml.md)
