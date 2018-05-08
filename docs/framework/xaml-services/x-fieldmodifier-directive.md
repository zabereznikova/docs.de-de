---
title: x:FieldModifier-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 1c7cb10a8021189aaac0ab8cfe5cc04ff8e67905
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier-Anweisung
Verwendung von XAML-Kompilierungsverhalten ändert, sodass Felder für benannte Objektverweise mit definiert sind <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> anstelle von Zugriff auf die <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Standardverhalten.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|*Public*|Die genaue Zeichenfolge übergeben, um anzugeben, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> im Vergleich zu <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> variiert in Abhängigkeit von der Code-Behind-Programmiersprache ab, der verwendet wird. Siehe Hinweise.|  
  
## <a name="dependencies"></a>Abhängigkeiten  
 Wenn eine XAML-Produktion verwendet `x:FieldModifier` an einer beliebigen Stelle, muss das Stammelement der XAML-Produktion Deklarieren einer [X: Class-Direktive](../../../docs/framework/xaml-services/x-class-directive.md).  
  
## <a name="remarks"></a>Hinweise  
 `x:FieldModifier` ist nicht relevant für die allgemeine Zugriffsebene einer Klasse oder der entsprechenden Member deklarieren. Es ist nur für XAML-Verarbeitungsverhalten relevant, wenn ein bestimmtes XAML-Objekt, das Bestandteil einer XAML-Produktion ist verarbeitet wird, wird ein Objekt, das potenziell im Objektdiagramm einer Anwendung zugegriffen werden kann. Standardmäßig wird der Feldverweis für ein solches Objekt, vertraulich behandelt die verhindert wird, dass Steuerelementconsumer Objektdiagramm direkt ändern. Stattdessen Steuerelementconsumer werden erwartet, dass das Ändern des Objektdiagramms mithilfe von Standardmustern, die von Programmiermodellen, erhalten das Layout-Stammelement, das untergeordnete Element Sammlungen, die dedizierten öffentliche Eigenschaften wie z. B. aktiviert sind und so weiter.  
  
 Der Wert für die `x:FieldModifier` Attribut variiert je nach Programmiersprache und ihren Zweck kann in bestimmten Frameworks variieren. Die zu verwendende Zeichenfolge hängt von verschiedenen Sprachen wie implementiert die <xref:System.CodeDom.Compiler.CodeDomProvider> und -Typkonverter, die zurückgegeben wird, um die Bedeutung für definieren <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> und <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, und gibt an, ob diese Sprache Groß-/Kleinschreibung beachtet wird.  
  
-   Für c#, die Zeichenfolge übergeben, um zu bestimmen <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ist `public`.  
  
-   Für Microsoft Visual Basic .NET, die Zeichenfolge übergeben, um zu bestimmen <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ist `Public`.  
  
-   Für [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], derzeit keine Ziele für XAML vorhanden; daher ist die Zeichenfolge übergeben nicht definiert.  
  
 Sie können auch angeben, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in c# `Friend` in Visual Basic) jedoch angeben <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist ungewöhnlich, da `NotPublic` wie das Verhalten bereits die Standardeinstellung ist.  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist das Standardverhalten, da sie selten ist, dass Code außerhalb der Assembly, die den XAML-Code kompiliert Zugriff auf ein Element mit XAML erstellt benötigt. WPF-Sicherheitsarchitektur zusammen mit XAML-Kompilierungsverhalten nicht Felder, die Elementinstanzen als öffentlich speichern deklarieren, es sei denn, Sie ausdrücklich Festlegen der `x:FieldModifier` den öffentlichen Zugriff zulässt.  
  
 `x:FieldModifier` ist nur relevant, für Elemente mit einem [X: Name-Direktive](../../../docs/framework/xaml-services/x-name-directive.md) , da dieser Name verwendet wird, um das Feld verweisen, nachdem es öffentlich ist.  
  
 Standardmäßig ist die partielle Klasse für das Stammelement öffentlich. Sie können jedoch machen es nicht öffentliche mithilfe der [X: ClassModifier-Direktive](../../../docs/framework/xaml-services/x-classmodifier-directive.md). Die [X: ClassModifier-Direktive](../../../docs/framework/xaml-services/x-classmodifier-directive.md) wirkt sich auch auf die Zugriffsebene der Instanz der Stammelementklasse. Sie können beide einfügen `x:Name` und `x:FieldModifier` im Stamm-Element, aber dies nur eine Kopie öffentliches Feld der "Root"-Element mit der Zugriffsebene der "true"-Klasse weiterhin von gesteuert [X: ClassModifier-Direktive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).  
  
## <a name="see-also"></a>Siehe auch  
 [XAML- und benutzerdefinierte Klassen für WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [Code-Behind und XAML in WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [x:Name-Anweisung](../../../docs/framework/xaml-services/x-name-directive.md)  
 [Erstellen einer WPF-Anwendung (WPF)](../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [x:ClassModifier-Anweisung](../../../docs/framework/xaml-services/x-classmodifier-directive.md)
