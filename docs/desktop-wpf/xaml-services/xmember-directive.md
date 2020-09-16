---
title: x:Member-Direktive
ms.date: 03/30/2017
ms.assetid: 4d8394ef-644c-4331-b6c5-be855d392980
ms.openlocfilehash: 1c5b26b405e574290af54b29b22fb5e19e4b6b95
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548246"
---
# <a name="xmember-directive"></a>x:Member-Direktive
Deklariert einen XAML-Member im Markup.

## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen

```xaml
<object x:Class="className">
  <x:Members>
    <x:Member Name="propertyName"/>
    additionalMembers
  </x:Members>
</object>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|`className`|Der Name der Sicherungsklasse oder partiellen Klasse für die XAML-Produktion.|
|`memberName`|Der Membername der Eigenschaft, die definiert wird.|

## <a name="remarks"></a>Hinweise

In der .net XAML-Dienst Implementierung. hat `x:Member` keine direkte Typunterstützung, wird jedoch durch die <xref:System.Windows.Markup.MemberDefinition>-Klasse unterstützt. In einem XAML-Knotenstream wird ein `x:Member`-Element als ein Member namens `Member` aus dem XAML-Namespace der XAML-Sprache dargestellt. Der Member `Member` enthält Attribute gemäß Deklaration durch Markup.

Die Bedeutung von `Name` und `Type` wird nicht auf der Ebene der .net XAML-Dienste zugewiesen. Sie sind im ursprünglichen XAML-Knotenstream als Zeichenfolgenwerte gespeichert, um später gemäß den Regeln interpretiert zu werden, die möglicherweise von bestimmten Frameworks erzwungen werden. Die Bedeutung kann, je nach Implementierung, an der Bedeutung eines XAML-Namens oder eines XAML-Typs ausgerichtet werden oder kann nur in einem Unterstützungstypsystem gültig sein.

Damit eine praktische Verwendung von `x:Members` als Mittel zum Angeben von Memberdefinitionen in Markup unterstützt wird, müssen die Member einer Klasse zugeordnet sein, die geändert werden kann. Das beabsichtigte Modell besteht darin, dass `x:Members` als ein Member eines Typs vorhanden ist, der eine `x:Class` angibt. Der Mechanismus zum Zuordnen von Typen und Membern oder zum Erstellen dynamischer Element Definitionen wird jedoch auf der Ebene der .net XAML-Dienste nicht unterstützt. Dies wird von einzelnen Frameworks übernommen, die Anwendungsmodelle haben, die Memberdefinitionen von XAML unterstützen. In der Regel sind, damit dieses Feature unterstützt wird, MSBUILD-Buildvorgänge erforderlich, die XAML als Markup kompilieren und es als CodeBehind integrieren oder reine Von-XAML-Assemblys generieren.

## <a name="xproperty-for-windows-workflow-foundation"></a>x:Property für Windows Workflow Foundation

Für Windows Workflow Foundation definiert `x:Property` die Member einer benutzerdefinierten Aktivität, die vollständig in XAML erstellt ist, oder XAML-definierte dynamische Member für einen Aktivitäts-Designer mit CodeBehind. `x:Class` muss auch für das Stammelement der XAML-Produktion angegeben werden. Dies ist keine Voraussetzung für die .net XAML-Dienst Ebene, sondern wird eine Anforderung, wenn die XAML-Produktion von den MSBuild-Buildaktionen geladen wird, die benutzerdefinierte Aktivitäten unterstützen, und Windows Workflow Foundation XAML im Allgemeinen. Windows Workflow Foundation verwendet nicht den reinen XAML-Typnamen als beabsichtigten Wert für das `x:Property` `Type` Attribut, sondern verwendet stattdessen eine Konvention, die hier nicht dokumentiert ist. Weitere Informationen finden Sie unter [DynamicActivity-Erstellung](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).
