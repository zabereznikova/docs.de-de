---
title: "x:TypeArguments Directive | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "x:TypeArguments"
  - "xTypeArguments"
  - "TypeArguments"
helpviewer_keywords: 
  - "x:TypeArguments attribute [XAML Services]"
  - "TypeArguments attribute in XAML [XAML Services]"
  - "XAML [XAML Services], x:TypeArguments attribute"
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
caps.latest.revision: 18
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 18
---
# x:TypeArguments Directive
Gibt Einschränkungstypargumente eines generischen Typs an den Konstruktor des generischen Typs weiter.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object x:TypeArguments="typeString" .../>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`object`|Eine Objektelementdeklaration eines XAML\-Typs, der von einem CLR\-generischen Typ unterstützt wird.  Wenn `object` auf einen XAML\-Typ verweist, der nicht aus dem standardmäßigen XAML\-Namespace stammt, erfordert `object` ein Präfix, um den XAML\-Namespace anzugeben, in dem `object` vorkommt.|  
|`typeString`|Eine Zeichenfolge, die einen oder mehrere XAML\-Typnamen als Zeichenfolgen deklariert, die die Typargumente für den CLR\-generischen Typ angeben.  Weitere Syntaxhinweise finden Sie in Hinweisen.|  
  
## Hinweise  
 In den meisten Fällen werden die als Informationselement in einer `typeString`\-Zeichenfolge verwendeten XAML\-Typen vorangestellt.  Typische Typen von generischen CLR\-Einschränkungen \(zum Beispiel <xref:System.Int32> und <xref:System.String>\) stammen aus den CLR\-Basisklassenbibliotheken.  Typischen frameworkspezifischen Standard\-XAML\-Namespaces werden jene Bibliotheken nicht zugeordnet; sie erfordern daher eine Präfixzuordnung für XAML\-Verwendung.  
  
 Sie können mehr als einen XAML\-Typnamen angeben, indem Sie ein Komma als Trennzeichen verwenden.  
  
 Wenn die generischen Einschränkungen selbst generische Typen verwenden, können die geschachtelten Einschränkungstypargumente in Klammern \(\) enthalten sein.  
  
 Beachten Sie, dass diese Definition von `x:TypeArguments` für .NET Framework\-XAML\-Dienste und das Verwenden von CLR\-Unterstützung spezifisch ist.  Eine Definition der Sprachebene finden Sie unter [\[MS\-XAML\] Abschnitt 5.3.11](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## Verwendungsbeispiele  
 Nehmen Sie für diese Beispiele an, dass die folgenden XAML\-Namespacedefinitionen deklariert werden:  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### List\<String\>  
 `<scg:List x:TypeArguments="sys:String" ...>` instanziert einen neuen <xref:System.Collections.Generic.List%601> mit einem <xref:System.String>\-Typargumente.  
  
### Dictionary\<String,String\>  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instanziert einen neuen <xref:System.Collections.Generic.Dictionary%602> mit zwei <xref:System.String>\-Typargumenten.  
  
### Queue\<KeyValuePair\<String,String\>\>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instanziiert eine neue <xref:System.Collections.Generic.Queue%601> mit einer Einschränkung von <xref:System.Collections.Generic.KeyValuePair%602> mit den inneren Einschränkungstypargumenten <xref:System.String> und <xref:System.String>.  
  
## XAML 2006\- und generische WPF\-XAML\-Verwendung  
 Bei XAML 2006\-Verwendung und XAML, das für WPF\-Anwendungen verwendet wird, bestehen im Allgemeinen die folgenden Einschränkungen für `x:TypeArguments` und generische Typverwendungen von XAML:  
  
-   Nur das Stammelement einer XAML\-Datei kann eine generische XAML\-Verwendung unterstützen, die auf einen generischen Typ verweist.  
  
-   Das Stammelement muss einem generischen Typ mit mindestens einem Typargument zugeordnet werden.  Ein Beispiel hierfür ist <xref:System.Windows.Navigation.PageFunction%601>.  Die Seitenfunktionen sind das primäre Szenario für XAML\-generische Verwendungsunterstützung in WPF.  
  
-   Das Stammelement XAML\-Objektelement für das generische Element muss auch eine partielle Klasse mittels `x:Class` deklarieren.  Dies gilt auch beim Definieren eines WPF\-Buildvorgangs.  
  
-   `x:TypeArguments` kann nicht auf geschachtelte generische Einschränkungen verweisen.  
  
## XAML 2009 oder XAML 2006 ohne WPF 3.0\/3.5\-Abhängigkeit  
 In .NET Framework\-XAML\-Diensten für XAML 2006 oder XAML 2009 wurden die WPF\-bezogenen Einschränkungen für die generische XAML\-Verwendung gelockert.  Sie können ein generisches Objektelement an einer beliebigen Position in XAML\-Markup instanziieren, die vom Unterstützungstypsystem und dem Objektmodell unterstützt werden können.  
  
 Wenn Sie zum Abrufen von XAML\-Typen für einheitliche Sprachenprimitiven XAML 2009 verwenden statt CLR\-Basistypen zuzuordnen, können Sie [integrierte Typen für häufige XAML\-Sprachprimitive](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) als Informationselemente in einer `typeString` verwenden.  Sie könnten z. B. Folgendes deklarieren \(Präfixzuordnungen werden nicht angezeigt, aber x ist der XAML\-Sprachnamespace in XAML 2009\):  
  
```  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 In WPF und mit [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] als Zielversion können Sie XAML 2009\-Funktionen zusammen mit `x:TypeArguments` verwenden, allerdings nur für Loose XAML \(nicht markupkompilierte XAML\).  Markupkompilierte XAML für WPF und die BAML\-Form von XAML unterstützen die XAML 2009\-Schlüsselwörter und \-Funktionen derzeit nicht.  Wenn Sie die XAML als Markup kompilieren müssen, müssen Sie unter den im Abschnitt "XAML 2006\- und generische WPF\-XAML\-Verwendung" genannten Einschränkungen operieren.  
  
## Siehe auch  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [x:Type Markup Extension](../../../docs/framework/xaml-services/x-type-markup-extension.md)   
 [Integrierte Typen für häufige XAML\-Sprachprimitive](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)   
 [Generics in XAML](../../../docs/framework/xaml-services/generics-in-xaml.md)