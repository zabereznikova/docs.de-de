---
title: x:Type-Markuperweiterung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
caps.latest.revision: 27
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: db56c2bcdca14b87de320dfe19a6c364c76ecef7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="xtype-markup-extension"></a>x:Type-Markuperweiterung
Die CLR stellt <xref:System.Type> Objekt, das den zugrunde liegenden Typ für einen angegebenen XAML-Typ ist.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`prefix`|Dies ist optional. Ein Präfix, das einen nicht standardmäßigen XAML-Namespace zugeordnet. Angeben eines Präfix ist häufig nicht erforderlich. Siehe Hinweise.|  
|`typeNameValue`|Erforderlich. Ein Typname der aktuellen XAML-Standardnamespace; oder das angegebene Präfix Wenn `prefix` angegeben wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `x:Type` Markuperweiterung hat eine ähnliche Funktion, die `typeof()` Operator in c# oder der `GetType` Operator in Microsoft Visual Basic.  
  
 Die `x:Type` Markuperweiterung gibt das Konvertierungsverhalten from-Zeichenfolgen für Eigenschaften, die der Typ akzeptieren <xref:System.Type>. Die Eingabe ist ein XAML-Typ. Die Beziehung zwischen der Verwendung von XAML-Typ der Eingabe und die Ausgabe CLR <xref:System.Type> ist, die die Ausgabe <xref:System.Type> ist die <xref:System.Xaml.XamlType.UnderlyingType%2A> der Eingabe <xref:System.Xaml.XamlType>, nach der Suche nach den erforderlichen <xref:System.Xaml.XamlType> basierend auf XAML-Schemakontext und die <xref:System.Windows.Markup.IXamlTypeResolver>Dienst, der den Kontext bereitstellt.  
  
 In .NET Framework XAML Services wird die Handhabung dieser Markuperweiterung von definiert die <xref:System.Windows.Markup.TypeExtension> Klasse.  
  
 In bestimmten Frameworks Implementierungen, einige Eigenschaften, die akzeptieren <xref:System.Type> als ein Wert direkt den Namen des Typs akzeptieren kann (den Zeichenfolgenwert des Typs `Name`). Dieses Verhalten zu implementieren, ist jedoch ein komplexes Szenario. Beispiele finden Sie im Abschnitt "Hinweise zur WPF-Verwendung" folgt.  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `x:Type`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.Markup.TypeExtension.TypeName%2A>-Wert der zugrunde liegenden <xref:System.Windows.Markup.TypeExtension>-Erweiterungsklasse zugeordnet. Unter Verwendung von XAML-Standardschemakontext für .NET Framework-XAML-Dienste, die auf CLR-Typen basiert, ist der Wert dieses Attributs die <xref:System.Reflection.MemberInfo.Name%2A> des gewünschten Typs oder die enthält <xref:System.Reflection.MemberInfo.Name%2A> für einen nicht standardmäßigen XAML-Namespace ein Präfix vorangestellt Zuordnung.  
  
 Die `x:Type` Markuperweiterung in die Syntax der Object-Element verwendet werden kann. In diesem Fall geben Sie den Wert der <xref:System.Windows.Markup.TypeExtension.TypeName%2A> Eigenschaft ist erforderlich, um die Erweiterung zu initialisieren.  
  
 Die `x:Type` Markuperweiterung kann auch als verbose-Attribut verwendet werden; diese Verwendung ist jedoch nicht typisch: `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
  
### <a name="default-xaml-namespace-and-type-mapping"></a>Standard-XAML-Namespace und Zuordnung  
 Die Verwendung von XAML-Standardnamespace für WPF-Programmierung enthält die meisten XAML-Typen für typische Verwendung von XAML-Szenarien benötigten; aus diesem Grund können Sie häufig Präfixe vermeiden, wenn XAML-Werte zu verweisen. Sie müssen möglicherweise ein Präfix zuordnen, wenn Sie einen Typ verweist, aus einer benutzerdefinierten Assembly oder für Typen, die in einer WPF-Assembly vorhanden sein, aber von einem CLR-Namespace, der nicht dem XAML-Standardnamespace zugeordnet sind. Weitere Informationen über Präfixe, XAML-Namespaces und Zuordnen von CLR-Namespaces finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF-XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### <a name="type-properties-that-support-typename-as-string"></a>Geben Sie die Eigenschaften dieser Unterstützung Typename-als-Zeichenfolge  
 WPF unterstützt Techniken, mit denen die Angabe des Werts einiger Eigenschaften des Typs <xref:System.Type> ohne eine `x:Type` Markuperweiterungsverwendung. Stattdessen können Sie den Wert als Zeichenfolge angeben, die den Typ benennt. Beispiele hierfür sind <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> und <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>. Unterstützung für dieses Verhalten wird nicht durch den Einsatz von Typkonvertern oder Markuperweiterungen bereitgestellt. Stattdessen ist dies ein Deferral-Verhalten über implementiert <xref:System.Windows.FrameworkElementFactory>.  
  
 Silverlight unterstützt eine ähnliche Konvention. In der Tat Silverlight unterstützt derzeit keine `{x:Type}` in der XAML-sprachunterstützung und akzeptiert keine `{x:Type}` Verwendungen außerhalb von wenigen Fällen, die zur Unterstützung von XAML-WPF-Silverlight Migration vorgesehen sind. Aus diesem Grund ist das Verhalten der Typname als Zeichenfolge in alle Silverlight-Eigenschaft "native"-Evaluierung integriert, in dem eine <xref:System.Type> ist der Wert.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 bietet zusätzliche Unterstützung für generische Typen und das Funktionsverhalten von ändert `x:TypeArguments` und `x:Type` zur Bereitstellung dieser Unterstützung.  
  
-   `x:TypeArguments` und das zugeordnete Objekt-Element für eine generische Objektinstanziierung kann auf andere Elemente als Stamm. Weitere Informationen finden Sie im Abschnitt "XAML 2009" von [X: TypeArguments-Direktive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
-   XAML 2009 unterstützt eine Syntax zum Angeben von Einschränkung eines generischen Typs in Markup. Dies kann verwendet werden, durch `x:TypeArguments`, von `x:Type`, oder indem Sie die beiden Funktionen sollten in Kombination.  
  
-   WPF-XAML-Implementierung, die bei der Verarbeitung von XAML 2009 für Load auch diese Funktion auf die implizite Typkonvertierungsverhalten für bestimmte Frameworkeigenschaften sorgt, mit dem Typ <xref:System.Type>.  
  
 In WPF können Sie XAML 2009-Funktionen verwenden, jedoch nur für loose XAML (, das nicht markupkompiliert ist). Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Style>  
 [Erstellen von Formaten und Vorlagen](../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Übersicht über XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Markuperweiterungen und WPF-XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
