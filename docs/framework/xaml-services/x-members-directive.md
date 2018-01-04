---
title: x:Members-Anweisung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e76f539e713f3d21751de18c86cc2dcebf99f570
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="xmembers-directive"></a>x:Members-Anweisung
Enthält eine Menge von Elementen, die im Markup definiert werden und gelten für die X: Class des übergeordneten Elements.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```  
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
|`oneOrMoreMembers`|Ein oder mehrere Objektelemente, die Memberdefinitionen darstellen. In der Regel sind diese `x:Property` Objektelemente. Siehe Hinweise.|  
  
## <a name="remarks"></a>Hinweise  
 In der .NET Framework-XAML-Dienste-Implementierung ist keine Sicherungsklasse oder zugrunde liegenden Schnittstellenmember-Implementierung für `x:Members`. `x:Members`ist ein spezieller XAML-Member, der als ein Element auf einen beliebigen Typ vorhanden sein kann. In einem XAML-Knotenstream `x:Members` wird dargestellt, wie ein Element mit dem Namen `Members`, aus der XAML-Namespace der XAML-Sprache. Das Element `Members` enthält eine schreibgeschützte generische Liste von `Member` Objekte. Im typischen Markup werden die einzelnen Mitglieder angegeben, als `x:Property` Eigenschaftenelemente. `x:Property`ist ein feiner abgestimmte Typ speziell für Eigenschaften von Typen und abfrageansichtsausdrucks `x:Member`. Weitere Informationen finden Sie unter [X: Property-Direktive](../../../docs/framework/xaml-services/x-property-directive.md).  
  
 Damit eine praktische Verwendung von `x:Members` als Mittel zum Angeben von Memberdefinitionen in Markup unterstützt wird, müssen die Member einer Klasse zugeordnet sein, die geändert werden kann. Das beabsichtigte Modell besteht darin, dass `x:Members` als ein Member eines Typs vorhanden ist, der eine `x:Class` angibt. Der Mechanismus zum Zuordnen von Typen und Membern oder zum Erstellen von dynamischen Memberdefinitionen wird jedoch auf der Ebene der .NET Framework-XAML-Dienste nicht unterstützt. Dies wird von einzelnen Frameworks übernommen, die Anwendungsmodelle haben, die Memberdefinitionen von XAML unterstützen. In der Regel sind, damit dieses Feature unterstützt wird, MSBUILD-Buildvorgänge erforderlich, die XAML als Markup kompilieren und es als CodeBehind integrieren oder reine Von-XAML-Assemblys generieren.  
  
## <a name="xmembers-for-windows-workflow-foundation"></a>X: Members für Windows Workflow Foundation  
 Für Windows Workflow Foundation `x:Members` enthält die Elemente einer benutzerdefinierten Aktivität zusammengesetzt vollständig in XAML oder in XAML-definierte dynamische Member für einen Aktivitäts-Designer mit CodeBehind. `x:Class` muss auch für das Stammelement der XAML-Produktion angegeben werden. Dies ist keine Anforderung auf der Ebene der .NET Framework-XAML-Dienste, wird jedoch eine Anforderung, wenn die XAML-Produktion von MSBUILD-Buildvorgängen geladen wird, die benutzerdefinierte Aktivitäten und Windows Workflow Foundation-XAML im Allgemeinen unterstützen. `x:Members`muss das erste untergeordnete Element im Markup der Object-Element, das deklariert die `x:Class`.
