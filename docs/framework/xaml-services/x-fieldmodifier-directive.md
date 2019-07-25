---
title: x:FieldModifier-Anweisung
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 646ad1ca99d83f9fb2994f3c394eca27a60c0eac
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484726"
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier-Anweisung
Ändert das XAML-Kompilierungs Verhalten, sodass Felder für benannte Objekt Verweise mit <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> Access anstelle <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> des Standard Verhaltens definiert werden.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|*Public*|Die genaue Zeichenfolge, die Sie <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> an <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> übergeben, wenn Sie angeben, oder variiert, hängt von der verwendeten Code-Behind-Programmiersprache ab. Siehe Hinweise.|  
  
## <a name="dependencies"></a>Abhängigkeiten  
 Wenn eine XAML-Produktion `x:FieldModifier` einen beliebigen Speicherort verwendet, muss das Stamm Element dieser XAML-Produktion eine [x:Class-Direktive](x-class-directive.md)deklarieren.  
  
## <a name="remarks"></a>Hinweise  
 `x:FieldModifier`ist für das Deklarieren der allgemeinen Zugriffsebene einer Klasse oder ihrer Member nicht relevant. Sie ist nur für das XAML-Verarbeitungs Verhalten relevant, wenn ein bestimmtes XAML-Objekt, das Teil einer XAML-Produktion ist, verarbeitet wird, und wird zu einem Objekt, auf das im Objekt Diagramm einer Anwendung möglicherweise zugegriffen werden kann. Standardmäßig wird der Feldverweis für ein solches Objekt als privat gespeichert, wodurch verhindert wird, dass Steuerungs Consumer das Objekt Diagramm direkt ändern können. Stattdessen wird erwartet, dass Steuerungs Consumer das Objekt Diagramm mithilfe von Standard Mustern ändern, die von Programmier Modellen aktiviert werden, z. b. durch Abrufen des Layoutstamms, der untergeordneten Element Auflistungen, der dedizierten öffentlichen Eigenschaften usw.  
  
 Der Wert `x:FieldModifier` des-Attributs variiert je nach Programmiersprache, und sein Zweck kann sich in bestimmten Frameworks unterscheiden. Die zu verwendende Zeichenfolge hängt davon ab, wie <xref:System.CodeDom.Compiler.CodeDomProvider> die jeweilige Sprache implementiert, und die Typkonverter, die <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> zurück <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>gegeben werden, um die Bedeutung für und zu definieren  
  
- Für C# <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ist`public`die an zu über gebende Zeichenfolge.  
  
- Bei Microsoft Visual Basic .net <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ist `Public`die Zeichenfolge, die an übergeben werden soll,.  
  
- Für C++/CLI sind derzeit keine Ziele für XAML vorhanden. Daher ist die zu über gebende Zeichenfolge nicht definiert.  
  
 Sie können auch ( <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal` in C#, `Friend` in Visual Basic) angeben. die <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Angabe von ist `NotPublic` jedoch ungewöhnlich, da das Verhalten bereits der Standard ist.  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>ist das Standardverhalten, da es selten auftritt, dass Code außerhalb der Assembly, die den XAML-Code kompiliert hat, Zugriff auf ein XAML-erstelltes Element benötigt. Die `x:FieldModifier` WPF-Sicherheitsarchitektur und das XAML-Kompilierungs Verhalten deklarieren keine Felder, die Element Instanzen als öffentlich speichern, es sei denn, Sie legen ausdrücklich fest, um öffentlichen Zugriff zuzulassen.  
  
 `x:FieldModifier`ist nur für Elemente mit einer [x:Name-Direktive](x-name-directive.md) relevant, da dieser Name verwendet wird, um auf das Feld zu verweisen, nachdem es öffentlich ist.  
  
 Standardmäßig ist die partielle Klasse für das Stamm Element öffentlich. Sie können Sie jedoch nicht öffentlich machen, indem Sie die [x:ClassModifier-Direktive](x-classmodifier-directive.md)verwenden. Die [x:ClassModifier-Direktive](x-classmodifier-directive.md) wirkt sich auch auf die Zugriffsebene der Instanz der Stamm Element Klasse aus. Sie können sowohl `x:Name` als auch `x:FieldModifier` für das root-Element platzieren, aber dadurch wird nur eine öffentliche Feld Kopie des Stamm Elements erstellt, wobei die Zugriffsebene der echten Stamm Element Klasse weiterhin durch die [x:ClassModifier-Direktive](x-classmodifier-directive.md)gesteuert wird.  
  
## <a name="see-also"></a>Siehe auch

- [XAML- und benutzerdefinierte Klassen für WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Code-Behind und XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:Name-Anweisung](x-name-directive.md)
- [Erstellen einer WPF-Anwendung (WPF)](../wpf/app-development/building-a-wpf-application-wpf.md)
- [x:ClassModifier-Anweisung](x-classmodifier-directive.md)
