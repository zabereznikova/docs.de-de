---
title: Versions- und Updateüberlegungen für C#-Entwickler
description: Die Einführung neuer Sprachfeatures in Ihrer Bibliothek kann sich auf den Code auswirken, der sie verwendet.
ms.topic: reference
ms.date: 09/19/2018
ms.openlocfilehash: f7db7c79792d04bcf592bc1858e1f0f05cb34402
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88268126"
---
# <a name="version-and-update-considerations-for-c-developers"></a>Versions- und Updateüberlegungen für C#-Entwickler

Kompatibilität ist ein sehr wichtiges Ziel, wenn der Sprache C# neue Features hinzugefügt werden. In nahezu allen Fällen kann vorhandener Code problemlos mit einer neuen Compilerversion neu kompiliert werden.

Möglicherweise ist mehr Sorgfalt erforderlich, wenn Sie neue Sprachfeatures in einer Bibliothek übernehmen. Sie erstellen möglicherweise eine neue Bibliothek mit Features, die sich in der neuesten Version befinden, und müssen sicherstellen, dass Apps, die mit früheren Versionen des Compilers erstellt wurden, diese verwenden können. Oder Sie nehmen ein Upgrade einer vorhandenen Bibliothek vor, und viele Ihrer Benutzer verfügen möglicherweise noch nicht über Versionen mit dem Upgrade. Beim Treffen von Entscheidungen zur Übernahme neuer Features müssen Sie zwei Varianten von Kompatibilität unterscheiden: quellkompatibel und binärkompatibel.

## <a name="binary-compatible-changes"></a>Binärkompatible Änderungen

Änderungen an ihrer Bibliothek sind **binärkompatibel**, wenn Ihre aktualisierte Bibliothek ohne Neuerstellung der Anwendungen und Bibliotheken, die sie nutzen, verwendet werden kann. Abhängige Assemblys müssen nicht neu erstellt werden, und es sind keine Änderungen am Quellcode erforderlich. Binärkompatible Änderungen sind zugleich auch quellkompatible Änderungen.

## <a name="source-compatible-changes"></a>Quellkompatible Änderungen

Änderungen an Ihrer Bibliothek sind **quellkompatibel**, wenn die Anwendungen und Bibliotheken, die Ihre Bibliothek nutzen, keine Änderungen am Quellcode erfordern, die Quellen aber mit der neuen Version neu kompiliert werden müssen, um ordnungsgemäß zu funktionieren.

## <a name="incompatible-changes"></a>Inkompatible Änderungen

Wenn eine Änderung weder **quellkompatibel** noch **binärkompatibel** ist, sind Änderungen am Quellcode in Kombination mit einer erneuten Kompilierung in den abhängigen Bibliotheken und Anwendungen erforderlich.

## <a name="evaluate-your-library"></a>Bewerten Ihrer Bibliothek

Diese Kompatibilitätskonzepte betreffen die öffentlichen und geschützten Deklarationen für Ihre Bibliothek, nicht deren interne Implementierung. Die interne Übernahme beliebiger neuer Features ist immer **binärkompatibel**.  

Bei **binärkompatiblen** Änderungen steht neue Syntax zur Verfügung, die den gleichen kompilierten Code für öffentliche Deklarationen erzeugt wie die ältere Syntax. Beispielsweise ist das Ändern einer Methode in ein Ausdruckskörpermember eine **binärkompatible** Änderung:

Ursprünglicher Code:

```csharp
public double CalculateSquare(double value)
{
    return value * value;
}
```

Neuer Code:

```csharp
public double CalculateSquare(double value) => value * value;
```

Mit **quellkompatiblen** Änderungen wird Syntax eingeführt, die den kompilierten Code für ein öffentliches Member ändert, aber in einer Weise, die mit vorhandenen Aufrufsites kompatibel ist. Beispielsweise ist das Ändern einer Methodensignatur von einem Wertparameter in einen `in`-Verweisparameter quellkompatibel, aber nicht binärkompatibel:

Ursprünglicher Code:

```csharp
public double CalculateSquare(double value) => value * value;
```

Neuer Code:

```csharp
public double CalculateSquare(in double value) => value * value;
```

In den [Neuigkeiten](index.md)-Artikeln ist vermerkt, ob die Einführung eines Features, das sich auf öffentliche Deklarationen auswirkt, quellkompatibel oder binärkompatibel ist.
