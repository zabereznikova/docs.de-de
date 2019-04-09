---
title: x:FieldModifier-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: c20564bcf8a25b1b59887fbefe6419671e0d6c03
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144546"
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier-Anweisung
XAML-Kompilierungsverhalten ändert, sodass Felder für benannte Objektverweise mit definiert werden <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> anstelle von Zugriff auf die <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Standardverhalten.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|*Public*|Die genaue Zeichenfolge, die Sie zum Festlegen von übergeben <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> im Vergleich zu <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> variiert in Abhängigkeit von der Code-Behind-Programmiersprache, die verwendet wird. Siehe Hinweise.|  
  
## <a name="dependencies"></a>Abhängigkeiten  
 Wenn eine XAML-Produktion verwendet `x:FieldModifier` , muss das Stammelement dieser XAML-Produktion deklarieren eine [X: Class-Anweisung](x-class-directive.md).  
  
## <a name="remarks"></a>Hinweise  
 `x:FieldModifier` ist nicht relevant, für das Deklarieren von Klassen oder Membern der allgemeinen Zugriffsebene. Es ist nur für XAML-Verarbeitungsverhalten relevant, wenn ein bestimmtes XAML-Objekt, das Teil einer XAML-Produktion verarbeitet wird, wird ein Objekt, das potenziell in ein Objektdiagramm aus einer Anwendung zugegriffen werden kann. In der Standardeinstellung der Feldverweis für ein solches Objekt "private", bleibt die verhindern, dass Steuerelementconsumer das Objektdiagramm direkt ändern. Stattdessen Steuerelementconsumer erwartet, das Objektdiagramm mithilfe von standard-Muster, die von Programmiermodellen, wie z. B. aktiviert werden, durch Abrufen der Layoutstamm, das untergeordnete Element elementauflistungen, die dedizierte öffentliche Eigenschaften, ändern und so weiter.  
  
 Der Wert für die `x:FieldModifier` -Attributs variiert je nach Programmiersprache, und ihr Zweck kann in bestimmten Frameworks variieren. Wie jede Sprache implementiert, die zu verwendende Zeichenfolge hängt die <xref:System.CodeDom.Compiler.CodeDomProvider> und der Typkonverter wird zurückgegeben, um die Bedeutung für definieren <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> und <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, und gibt an, ob die entsprechende Sprache Groß-/Kleinschreibung beachtet wird.  
  
-   Für c# und die Zeichenfolge übergeben, um zu bestimmen <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ist `public`.  
  
-   Für Microsoft Visual Basic .NET ist die Zeichenfolge übergeben, um zu bestimmen <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ist `Public`.  
  
-   Für [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], keine Ziele für XAML derzeit vorhanden; aus diesem Grund ist die Zeichenfolge übergeben nicht definiert.  
  
 Sie können auch angeben, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in C#, `Friend` in Visual Basic) jedoch Angabe <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist ungewöhnlich, dass da `NotPublic` wie das Verhalten bereits die Standardeinstellung ist.  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist das Standardverhalten, da sie nur selten ist, dass Code außerhalb der Assembly, die die XAML kompiliert Zugriff auf ein Element mit XAML erstellten benötigt. WPF-Sicherheitsarchitektur zusammen mit XAML-Kompilierungsverhalten nicht Felder zum Speichern von Elementinstanzen als öffentlich, deklarieren, es sei denn, Sie ausdrücklich Festlegen der `x:FieldModifier` den öffentlichen Zugriff zulässt.  
  
 `x:FieldModifier` gilt nur für Elemente mit einem [X: Name Directive](x-name-directive.md) , da der Name verwendet wird, auf das Feld verwiesen wird, nachdem er öffentlich ist.  
  
 Standardmäßig ist die partielle Klasse für das Stammelement öffentlich. Allerdings können Sie es machen nicht öffentliche mithilfe der [X: ClassModifier-Anweisung](x-classmodifier-directive.md). Die [X: ClassModifier-Anweisung](x-classmodifier-directive.md) wirkt sich auch auf die Zugriffsebene der Stammelementklasse-Instanz. Sie können beide einfügen `x:Name` und `x:FieldModifier` für den Stamm-Element, aber dies nur eine Kopie öffentliches Feld das Stammelement, mit der Zugriffsebene der "true"-Klasse weiterhin benutzergesteuert [X: ClassModifier-Anweisung](x-classmodifier-directive.md).  
  
## <a name="see-also"></a>Siehe auch

- [XAML- und benutzerdefinierte Klassen für WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Code-Behind und XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:Name-Anweisung](x-name-directive.md)
- [Erstellen einer WPF-Anwendung (WPF)](../wpf/app-development/building-a-wpf-application-wpf.md)
- [x:ClassModifier-Anweisung](x-classmodifier-directive.md)
