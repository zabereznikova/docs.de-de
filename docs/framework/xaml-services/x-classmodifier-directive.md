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
ms.openlocfilehash: a24277a4d5fbc4870157b6c8ba00ba71ba61e656
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837232"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier-Anweisung
Ändert das XAML-Kompilierungs Verhalten, wenn `x:Class` ebenfalls bereitgestellt wird. Anstatt eine partielle `class` zu erstellen, die über eine `Public` Zugriffsebene (Standardeinstellung) verfügt, wird der bereitgestellte `x:Class` mit einer `NotPublic` Zugriffsebene erstellt. Dieses Verhalten wirkt sich auf die Zugriffsebene für die-Klasse in den generierten Assemblys aus.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|*NotPublic*|Die genaue Zeichenfolge, die an übergeben werden soll, um <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> im Vergleich <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> anzugeben, hängt von der verwendeten Code-Behind-Programmiersprache ab. Siehe Hinweise.|  
  
## <a name="dependencies"></a>-Abhängigkeiten  
 [x:Class](x-class-directive.md) muss auch für dasselbe Element bereitgestellt werden, und dieses Element muss das Stamm Element in einer Seite sein. Weitere Informationen finden Sie unter [\[MS-XAML\] Abschnitt 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
## <a name="remarks"></a>Hinweise  
 Der Wert `x:ClassModifier` in .NET Framework der Verwendung von XAML-Diensten hängt von der Programmiersprache ab. Die zu verwendende Zeichenfolge hängt davon ab, wie die jeweilige Sprache die <xref:System.CodeDom.Compiler.CodeDomProvider> implementiert, und die Typkonverter, die zurückgegeben werden, um die Bedeutungen für <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> und <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>zu definieren, und ob die Groß-/Kleinschreibung  
  
- Für C#ist die an zu über gebende Zeichenfolge <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal`.  
  
- Für Microsoft Visual Basic .net ist die zu über gebende Zeichenfolge <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend`.  
  
- Für C++/CLI gibt es keine Ziele, die das Kompilieren von XAML unterstützen. Daher ist der zu Übergabe Wert nicht angegeben.  
  
 Sie können auch <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> angeben (`public` in C#, `Public` in Visual Basic); das Angeben von <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> erfolgt jedoch selten, da <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> bereits das Standardverhalten ist.  
  
 Andere Werte mit äquivalenten Zugriffs ebeneneinschränkungen für den Benutzercode, C#wie z. b. `private` in, sind für `x:ClassModifier` nicht relevant, da in XAML keine in XAML unterstützten Klassen Verweise unterstützt werden und der <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>-Modifizierer daher dieselbe Auswirkung hat.  
  
## <a name="security-notes"></a>Sicherheitshinweise  
 Die in `x:ClassModifier` deklarierte Zugriffsebene unterliegt weiterhin der Interpretation durch bestimmte Frameworks und deren Funktionen. WPF enthält Funktionen zum Laden und Instanziieren von Typen, bei denen `x:ClassModifier` `internal`ist, wenn von einer WPF-Ressource über einen Paket-URI-Verweis auf diese Klasse verwiesen wird. In diesem Fall und möglicherweise andere, wie Sie von anderen Frameworks implementiert werden, verlassen sich nicht ausschließlich auf `x:ClassModifier`, um alle möglichen instanziierungsversuche zu blockieren.  
  
## <a name="see-also"></a>Siehe auch

- [x:Class-Anweisung](x-class-directive.md)
- [Code-Behind und XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:FieldModifier-Anweisung](x-fieldmodifier-directive.md)
- [Sicherheit (WPF)](../wpf/security-wpf.md)
- [Aus WPF zu System.Xaml migrierte Typen](types-migrated-from-wpf-to-system-xaml.md)
