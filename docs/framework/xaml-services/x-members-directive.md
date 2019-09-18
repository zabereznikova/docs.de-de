---
title: x:Members-Anweisung
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: ca42079c1c40a8fb3b1ddfc8f4a6f742768fa9e1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053772"
---
# <a name="xmembers-directive"></a>x:Members-Anweisung
Enthält eine Reihe von Membern, die im Markup definiert sind und auf die x:-Klasse des übergeordneten Elements angewendet werden.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`className`|Der Name der Sicherungsklasse oder partiellen Klasse für die XAML-Produktion. Siehe Hinweise.|  
|`oneOrMoreMembers`|Ein oder mehrere Objekt Elemente, die Element Definitionen darstellen. In der Regel handelt `x:Property` es sich hierbei um Objekt Elemente. Siehe Hinweise.|  
  
## <a name="remarks"></a>Hinweise  
 In der .NET Framework XAML-Dienst Implementierung gibt es keine Unterstützungs Klasse oder zugrunde liegende Member- `x:Members`Implementierung für. `x:Members`ist ein spezieller XAML-Member, der als Member für einen beliebigen Typ vorhanden sein kann. In einem XAML-knotenstream `x:Members` wird im XAML- `Members`Namespace der XAML-Sprache als Member mit dem Namen dargestellt. Der Member `Members` enthält eine schreibgeschützte generische Liste von `Member` -Objekten. Im typischen Markup werden die einzelnen Member als `x:Property` Eigenschafts Elemente angegeben. `x:Property`ist ein genauerer Typ speziell für Eigenschaften von Typen, `x:Member`der zugewiesen werden kann. Weitere Informationen finden Sie unter [x:property-Direktive](x-property-directive.md).  
  
 Damit eine praktische Verwendung von `x:Members` als Mittel zum Angeben von Memberdefinitionen in Markup unterstützt wird, müssen die Member einer Klasse zugeordnet sein, die geändert werden kann. Das beabsichtigte Modell besteht darin, dass `x:Members` als ein Member eines Typs vorhanden ist, der eine `x:Class` angibt. Der Mechanismus zum Zuordnen von Typen und Membern oder zum Erstellen von dynamischen Memberdefinitionen wird jedoch auf der Ebene der .NET Framework-XAML-Dienste nicht unterstützt. Dies wird von einzelnen Frameworks übernommen, die Anwendungsmodelle haben, die Memberdefinitionen von XAML unterstützen. In der Regel sind, damit dieses Feature unterstützt wird, MSBUILD-Buildvorgänge erforderlich, die XAML als Markup kompilieren und es als CodeBehind integrieren oder reine Von-XAML-Assemblys generieren.  
  
## <a name="xmembers-for-windows-workflow-foundation"></a>x:Members für Windows Workflow Foundation  
 `x:Members` Enthält für Windows Workflow Foundation die Member einer benutzerdefinierten Aktivität, die vollständig in XAML erstellt wurde, oder XAML – definierte dynamische Member für einen Aktivitäts Designer mit Code Behind. `x:Class` muss auch für das Stammelement der XAML-Produktion angegeben werden. Dies ist keine Anforderung auf der Ebene der .NET Framework-XAML-Dienste, wird jedoch eine Anforderung, wenn die XAML-Produktion von MSBUILD-Buildvorgängen geladen wird, die benutzerdefinierte Aktivitäten und Windows Workflow Foundation-XAML im Allgemeinen unterstützen. `x:Members`muss das erste untergeordnete Element im Markup des Object-Elements sein, das `x:Class`deklariert.
