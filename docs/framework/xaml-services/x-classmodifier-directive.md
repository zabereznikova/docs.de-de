---
title: x:ClassModifier-Anweisung
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 5daff0567c1b1415fe994f6e39b4079cb2ab7346
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053818"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier-Anweisung
Ändert das XAML-Kompilierungs `x:Class` Verhalten, wenn ebenfalls bereitgestellt wird. Anstatt eine partielle `class` zu erstellen, die über eine `Public` Zugriffsebene (Standardeinstellung) verfügt, wird `x:Class` der bereitgestellte mit `NotPublic` einer Zugriffsebene erstellt. Dieses Verhalten wirkt sich auf die Zugriffsebene für die-Klasse in den generierten Assemblys aus.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|*NotPublic*|Die genaue Zeichenfolge, die an <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> übergeben werden soll, und variiert abhängig von der verwendeten Programmiersprache Code-Behind. Siehe Hinweise.|  
  
## <a name="dependencies"></a>Abhängigkeiten  
 [x:Class](x-class-directive.md) muss auch für dasselbe Element bereitgestellt werden, und dieses Element muss das Stamm Element in einer Seite sein. Weitere Informationen finden [ \[Sie im Abschnitt zu MS-\] XAML 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Hinweise  
 Der Wert von `x:ClassModifier` in .NET Framework Verwendung der XAML-Dienste hängt von der Programmiersprache ab. Die zu verwendende Zeichenfolge hängt davon ab, wie <xref:System.CodeDom.Compiler.CodeDomProvider> die jeweilige Sprache implementiert, und die Typkonverter, die <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> zurück <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>gegeben werden, um die Bedeutung für und zu definieren  
  
- Für C# <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist`internal`die an zu über gebende Zeichenfolge.  
  
- Bei Microsoft Visual Basic .net <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist `Friend`die Zeichenfolge, die an übergeben werden soll,.  
  
- Für C++/CLI gibt es keine Ziele, die das Kompilieren von XAML unterstützen. Daher ist der zu Übergabe Wert nicht angegeben.  
  
 Sie können auch ( <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `public` in C#, `Public` in Visual Basic) angeben. die Angabe <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> von ist jedoch nur selten durch <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> geführt, da bereits das Standardverhalten ist.  
  
 Andere Werte mit äquivalenten Zugriffs ebeneneinschränkungen für den Benutzer `private` Code C#, z. b. `x:ClassModifier` in, sind für nicht relevant, da in XAML keine in XAML <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> unterstützten Klassen Verweise unterstützt werden und der-Modifizierer daher dieselbe Auswirkung hat. .  
  
## <a name="security-notes"></a>Sicherheitshinweise  
 Die Zugriffsebene, wie Sie `x:ClassModifier` in deklariert wird, unterliegt weiterhin der Interpretation durch bestimmte Frameworks und deren Funktionen. WPF enthält Funktionen zum Laden und Instanziieren von Typen `x:ClassModifier` , `internal`bei denen ist, wenn auf diese Klasse von einer WPF-Ressource über einen Paket-URI-Verweis verwiesen wird. In diesem Fall und möglicherweise andere, wie Sie von anderen Frameworks implementiert werden, verlassen sich nicht ausschließlich `x:ClassModifier` darauf, dass alle möglichen instanziierungsversuche blockiert werden.  
  
## <a name="see-also"></a>Siehe auch

- [x:Class-Anweisung](x-class-directive.md)
- [Code-Behind und XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:FieldModifier-Anweisung](x-fieldmodifier-directive.md)
- [Sicherheit (WPF)](../wpf/security-wpf.md)
- [Aus WPF zu System.Xaml migrierte Typen](types-migrated-from-wpf-to-system-xaml.md)
