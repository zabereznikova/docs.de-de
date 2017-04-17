---
title: "x:Static Markup Extension | Microsoft Docs"
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
  - "StaticExtension"
  - "xStatic"
  - "x:Static"
helpviewer_keywords: 
  - "x:Static markup extension [XAML Services]"
  - "Static markup extension in XAML [XAML Services]"
  - "XAML [XAML Services], x:Static markup extension"
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
caps.latest.revision: 25
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 25
---
# x:Static Markup Extension
Verweist auf alle statischen By\-Value\-Codeentitäten, die auf [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]\-kompatible Weise definiert sind.  Die statische Eigenschaft, auf die verwiesen wird, kann verwendet werden, um den Wert einer Eigenschaft in XAML bereitzustellen.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`prefix`|Optional.  Ein Präfix, das sich auf einen zugeordneten, nicht standardmäßigen XAML\-Namespace bezieht.  `prefix` wird explizit in der Verwendung angezeigt, da Sie selten statische Eigenschaften, die von einem Standard\-XAML\-Namespace kommen, mit Verweisen versehen.  Siehe Hinweise.|  
|`typeName`|Erforderlich.  Der Name des Typs, der den gewünschten statischen Member definiert.|  
|`staticMemberName`|Erforderlich.  Der Name des gewünschten statischen Wertmembers \(eine Konstante, eine statische Eigenschaft, ein Feld oder ein Enumerationswert\).|  
  
## Hinweise  
 Die referenzierte Codeentität muss eines der folgenden Elemente sein:  
  
-   Eine Konstante  
  
-   Eine statische Eigenschaft  
  
-   Ein Feld  
  
-   Ein Enumerationswert  
  
 Die Angabe einer beliebigen anderen Codeentität, z. B. eine nicht statische Eigenschaft, führt zu einem Kompilierzeitfehler, wenn das XAML kompiliertes Markup ist, oder zu einer XAML\-Ladezeitanalyseausnahme.  
  
 Sie können `x:Static`\-Verweise für statische Felder oder Eigenschaften erstellen, die sich nicht im standardmäßigen XAML\-Namespace für das aktuelle XAML\-Dokument befinden. Hierzu ist jedoch eine Präfixzuordnung erforderlich.  XAML\-Namespaces werden fast immer auf dem Stammelement des XAML\-Dokuments definiert.  
  
 Die Suchvorgänge für statische Eigenschaften können von .NET Framework\-XAML\-Diensten und ihren XAML\-Readern und XAML\-Writern ausgeführt werden, wenn sie mit dem Standard\-XAML\-Schemakontext ausgeführt werden.  Dieser XAML\-Schemakontext kann die notwendigen statischen Werte mithilfe CLR\-Reflektion für Objektdiagrammkonstruktion bereitstellen.  Das angegebene `typeName`\-Objekt ist eigentlich ein XAML\-Typname und kein CLR\-Typname, obwohl diese im Wesentlichen die gleichen Namen sind, wenn der Standard\-XAML\-Schemakontext oder alle vorhandenen CLR\-basierten Frameworks, die XAML implementieren, verwendet werden.  
  
 Seien Sie vorsichtig, wenn Sie `x:Static`\-Verweise machen, die nicht direkt der Typ eines Eigenschaftswertes sind.  In der XAML\-Verarbeitungssequenz rufen bereitgestellte Werte von einer Markuperweiterung keine weitere Wertkonvertierung auf.  Dies gilt, auch wenn der Verweis auf `x:Static` eine Textzeichenfolge erstellt, und eine Wertkonvertierung für Attributwerte auf Grundlage der Textzeichenfolge entweder für diesen bestimmten Member oder irgendwelche Memberwerte des Rückgabetyps erfolgt.  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.  Das Zeichenfolgentoken, das auf die `x:Static`\-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.Markup.StaticExtension.Member%2A>\-Wert der zugrunde liegenden <xref:System.Windows.Markup.StaticExtension>\-Erweiterungsklasse zugeordnet.  
  
 Es gibt zwei andere XAML\-Verwendungen, die technisch möglich sind.  Diese Verwendungen sind jedoch weniger gängig, da sie unnötig ausführlich sind:  
  
 **Objektelementsyntax:** `<x:Static Member="``prefix``:``typeName``.``staticMemberName``" .../>`  
  
 **Zuschreiben von Syntax mit expliziter Membereigenschaft für Initialisierungszeichenfolge:** `<` `object` `` `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName` `}" .../>` staticMemberName. typeName: prefix \="{x:Static Member\= property   object  
  
 Bei der Implementierung von .NET Framework XAML Services wird die Handhabung dieser Markuperweiterung durch die Klasse <xref:System.Windows.Markup.StaticExtension> definiert.  
  
 `x:Static` ist eine Markuperweiterung.  Alle Markuperweiterungen in XAML verwenden die Zeichen `{` und `}` in der Attributsyntax. Dies ist die Konvention, durch die ein XAML\-Prozessor erkennt, dass eine Markuperweiterung einen Wert angeben muss.  Weitere Informationen zu Markuperweiterungen finden Sie unter [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
## Hinweise zur WPF\-Verwendung  
 Der Standard\-XAML\-Namespace, den Sie für WPF\-Programmierung verwenden, enthält viele nützliche statische Eigenschaften nicht, und die meisten der nützlichen statischen Eigenschaften haben Unterstützung z. B. Typkonverter, die die Verwendung erleichtern, ohne `{x:Static}` zu benötigen.  Für statische Eigenschaften müssen Sie für einen XAML\-Namespace ein Präfix zuordnen, wenn eins von Folgendem gilt:  
  
-   Sie verweisen auf einen Typ, der in WPF vorhanden ist, der aber nicht Bestandteil des standardmäßigen XML\-Namespace von WPF ist \([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]\).  Dies ist häufig der Fall, wenn `x:Static` verwendet wird.  Sie können beispielsweise einen `x:Static`\-Verweis mit einer XAML\-Namespacezuordnung zu dem <xref:System>\-CLR\-Namespace und mscorlib\-Assembly verwenden, um auf die statischen Eigenschaften der <xref:System.Environment>\-Klasse zu verweisen.  
  
-   Sie verweisen auf einen Typ aus einer benutzerdefinierten Assembly.  
  
-   Sie verweisen auf einen Typ, der in einer WPF\-Assembly vorhanden ist. Der Typ befindet sich jedoch innerhalb eines CLR\-Namespace, der nicht als Bestandteil des WPF\-Standard\-XAML\-Namespace zugeordnet wurde.  Die Zuordnung von CLR\-Namespaces in den Standard\-XAML\-Namespace für WPF wird von Definitionen in den verschiedenen WPF\-Assemblys ausgeführt \(weitere Informationen zu diesem Konzept finden Sie unter [XAML\-Namespaces und Namespacezuordnung für WPF\-XAML](../../../ocs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)\).  Nicht zugeordnete CLR\-Namespaces kann vorhanden sein, wenn der CLR\-Namespace hauptssächlich aus Klassendefinitionen besteht, die normalerweise nicht für XAML bestimmt sind, wie z. B. <xref:System.Windows.Threading>.  
  
 Weitere Informationen über die Verwendung von Präfixen und XAML\-Namespaces für WPF finden Sie unter [XAML\-Namespaces und Namespacezuordnung für WPF\-XAML](../../../ocs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
## Siehe auch  
 [x:Type Markup Extension](../../../docs/framework/xaml-services/x-type-markup-extension.md)   
 [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)