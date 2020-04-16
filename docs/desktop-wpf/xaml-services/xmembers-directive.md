---
title: x:Members-Anweisung
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: c751a4f1cdea8dce7ef5165f5225ab3a825c7344
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432725"
---
# <a name="xmembers-directive"></a>x:Members-Anweisung
Enthält eine Gruppe von Membern, die in Markup definiert sind und auf die x:Klasse des übergeordneten Elements angewendet werden.

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
|`oneOrMoreMembers`|Ein oder mehrere Objektelemente, die Elementdefinitionen darstellen. In der `x:Property` Regel handelt es sich dabei um Objektelemente. Siehe Hinweise.|

## <a name="remarks"></a>Bemerkungen

In der .NET XAML Services-Implementierung gibt es `x:Members`keine Sicherungsklasse oder zugrunde liegende Memberimplementierung für . `x:Members`ist ein spezielles XAML-Member, das als Member für jeden Typ vorhanden sein kann. In einem XAML-Knotenstream `x:Members` wird aus `Members`dem XAML-Sprach-XAML-Namespace als Member mit dem Namen dargestellt. Das `Members` Element enthält eine schreibgeschützte `Member` generische Liste von Objekten. In typischem Markup werden `x:Property` die einzelnen Elemente als Eigenschaftselemente angegeben. `x:Property`ist ein präziserer Typ speziell für Eigenschaften `x:Member`von Typen und kann zu zu . Weitere Informationen finden Sie unter [x:Property Directive](xproperty-directive.md).

Damit eine praktische Verwendung von `x:Members` als Mittel zum Angeben von Memberdefinitionen in Markup unterstützt wird, müssen die Member einer Klasse zugeordnet sein, die geändert werden kann. Das beabsichtigte Modell besteht darin, dass `x:Members` als ein Member eines Typs vorhanden ist, der eine `x:Class` angibt. Der Mechanismus zum Zuordnen von Typen und Membern oder zum Erstellen dynamischer Memberdefinitionen wird jedoch auf .NET XAML Services-Ebene nicht unterstützt. Dies wird von einzelnen Frameworks übernommen, die Anwendungsmodelle haben, die Memberdefinitionen von XAML unterstützen. In der Regel sind, damit dieses Feature unterstützt wird, MSBUILD-Buildvorgänge erforderlich, die XAML als Markup kompilieren und es als CodeBehind integrieren oder reine Von-XAML-Assemblys generieren.

## <a name="xmembers-for-windows-workflow-foundation"></a>x:Mitglieder für Windows Workflow Foundation

Enthält für Windows `x:Members` Workflow Foundation die Mitglieder einer benutzerdefinierten Aktivität, die vollständig in XAML oder XAML-definierten dynamischen Membern für einen Aktivitäts-Designer mit CodeBehind besteht. `x:Class` muss auch für das Stammelement der XAML-Produktion angegeben werden. Dies ist keine Anforderung auf .NET XAML Services-Ebene, wird aber zu einer Anforderung, wenn die XAML-Produktion von den MSBUILD-Buildaktionen geladen wird, die benutzerdefinierte Aktivitäten und Windows Workflow Foundation XAML im Allgemeinen unterstützen. `x:Members`muss das erste untergeordnete Element im Markup des `x:Class`Objektelements sein, das die deklariert.
