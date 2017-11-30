---
title: Die Beziehung zwischen den Funktionen der Programmiersprache und Bibliothekstypen | Microsoft Docs
description: "Sprachfunktionen basieren häufig auf Bibliothekstypen für die Implementierung. Diese Beziehung zu verstehen."
keywords: C#-Sprachentwurf-Standardbibliothek
author: billwagner
ms.author: wiwagn
ms.date: 07/20/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 93fd26a72743fcf45df3904cb8d0c787d8a228a8
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2017
---
# <a name="relationships-between-language-features-and-library-types"></a>Beziehungen zwischen den Funktionen der Programmiersprache und Bibliothekstypen

Der C#-Sprachendefinition erfordert eine Standardbibliothek auf bestimmte Typen und bestimmte zugängliche Member für diese Typen verfügen. Der Compiler generiert Code, der diese erforderlichen Typen und Member für viele verschiedene Sprachfunktionen verwendet. Falls erforderlich, stehen die NuGet-Pakete, die enthalten Typen, die für neuere Versionen der Sprache benötigt wird, wenn die Schreiben von Code für Umgebungen, in denen diese Typen oder Member nicht noch bereitgestellt wurden.

Dieser Abhängigkeit von Funktionen der Standardbibliothek wurde Teil der C#-Sprache seit der ersten Version. In dieser Version enthalten Beispiele:

* <xref:System.Exception>– verwendet für alle vom Compiler generierte Ausnahmen.
* <xref:System.String>-die C#- `string` Typ ist ein Synonym für <xref:System.String>.
* <xref:System.Int32>-Synonym für `int`.

Diese erste Version war einfach: der Compiler und die Standardbibliothek geliefert zusammen, und es wurde nur eine Version der einzelnen.

Nachfolgende Versionen von c# haben gelegentlich neue Typen oder Member Abhängigkeiten hinzugefügt. Beispiele hierfür sind: <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> und <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>. C#-7.0 weiterhin dies durch Hinzufügen einer Abhängigkeit auf <xref:System.ValueTuple> zum Implementieren der [Tupel](../tuples.md) Sprachfunktion.

Das Entwurfsteam Sprache funktioniert auf um die Typen und Member, die in eine kompatible Standardbibliothek erforderlich die Angriffsfläche zu reduzieren. Das Ziel wird für eine fehlerfreie Entwurf verteilt, auf dem neuen Bibliotheksfunktionen nahtlos in die Sprache integriert sind. Es werden neue Funktionen in zukünftigen Versionen von c#, die erfordern neue Typen und Member in eine Standardbibliothek. Es ist wichtig zu verstehen, wie diese Abhängigkeiten in Ihre Arbeit zu verwalten.

## <a name="managing-your-dependencies"></a>Verwalten Ihre Abhängigkeiten

C#-Compiler-Tools werden jetzt von den Freigabezyklus der Bibliotheken .NET auf unterstützten Plattformen entkoppelt. Tatsächlich haben unterschiedliche .NET Bibliotheken unterschiedliche Versionszyklen: .NET Framework auf Windows Relesed als Windows Update, .NET Core auf einem separaten Zeitplan, und die Xamarin-Versionen der Bibliothek die Updates im Lieferumfang der Xamarin-Tools für jede Zielplattform geliefert wird.

Sie wird nicht den Großteil der Optimierungszeit, diese Änderungen beachten. Allerdings bei der Arbeit mit einer neueren Version der Sprache, die Features nicht erfordert noch in der .NET-Bibliotheken für diese Plattform, verweisen die NuGet-Pakete zum Bereitstellen dieser neuen Typen.
Die Plattformen, die Ihre app unterstützt bei Neuinstallationen Framework aktualisiert werden, können Sie den zusätzlichen Verweis entfernen.

Diese Trennung bedeutet, dass Sie neue Sprachfeatures verwenden können, selbst wenn Sie Computer, die möglicherweise keine entsprechende Framework abzielen.
