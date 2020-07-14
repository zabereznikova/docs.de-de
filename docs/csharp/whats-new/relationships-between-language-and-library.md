---
title: Die Beziehung zwischen Sprachfeatures und Bibliothekstypen | Microsoft-Dokumentation
description: Die Implementierung von Sprachfeatures hängt oft von Bibliothekstypen ab. Diese Beziehung wird in diesem Artikel erläutert.
ms.date: 07/20/2017
ms.openlocfilehash: abf15385da3756c35db2df822cc2e11e9edf5758
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174100"
---
# <a name="relationships-between-language-features-and-library-types"></a>Die Beziehung zwischen Sprachfeatures und Bibliothekstypen

Die C#-Sprachdefinition erfordert eine Standardbibliothek, damit bestimmte Typen und bestimmte zugängliche Members für diese Typen verfügbar sind. Der Compiler generiert Code, der die erforderlichen Typen und Members für viele verschiedene Sprachfeatures verwendet. Beim Schreiben von Code für Umgebungen, für die diese Typen und Members noch nicht bereitgestellt wurden, stehen bei Bedarf NuGet-Pakete zur Verfügung, die Typen enthalten, die für neuere Versionen der Sprache erforderlich sind.

Diese Abhängigkeit von den Funktionen der Standardbibliothek ist seit der ersten Version Teil der Sprache „C#“. In dieser Version sind folgende Beispiele enthalten:

* <xref:System.Exception>: wird für alle vom Compiler generierten Ausnahmen verwendet.
* <xref:System.String>: Der C#-Typ `string` stellt ein Synonym für <xref:System.String> dar.
* <xref:System.Int32>: Synonym von `int`.

Diese erste Version war einfach, denn der Compiler und die Standardbibliothek waren beide enthalten, und von beiden gab es nur eine Version.

Bei nachfolgenden Versionen von C# wurden den Abhängigkeiten gelegentlich neue Typen oder Members hinzugefügt. Beispiele dafür sind <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> und <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>. In C# 7.0 wird dies fortgesetzt, indem die Abhängigkeit von <xref:System.ValueTuple> hinzugefügt wird, um das Sprachfeature für [Tupels](../language-reference/builtin-types/value-tuples.md) hinzuzufügen.

Das Entwurfsteam für die Sprache arbeitet daran, die Oberfläche der Typen und Members zu verringern, die für eine kompatible Standardbibliothek erforderlich sind. Das Ziel ist ein übersichtliches Design, bei dem neue Bibliotheksfeatures nahtlos in die Sprache integriert werden können. In zukünftigen Versionen von C# werden neue Features hinzugefügt, die neue Typen und Members in einer Standardbibliothek erfordern. Es ist wichtig, ein Verständnis dafür zu entwickeln, wie Sie diese Abhängigkeiten in Ihrer Arbeit verwalten.

## <a name="managing-your-dependencies"></a>Verwalten Ihrer Abhängigkeiten

C#-Compilertools werden nun vom Releasezyklus der .NET-Bibliotheken auf den unterstützten Plattformen entkoppelt. Unterschiedliche .NET-Bibliotheken weisen unterschiedliche Releasezyklen auf. So wird .NET Framework unter Windows als Windows Update veröffentlicht, während .NET Core einem anderen Zeitplan folgt und die Xamarin-Versionen der Bibliotheksupdates in den Xamarin-Tools für jede Zielplattform enthalten sind.

In den meisten Fällen werden Sie diese Änderungen nicht bemerken. Wenn Sie jedoch mit einer neueren Version der Sprache arbeitet, die Features erfordert, die noch nicht in den .NET-Bibliotheken auf dieser Plattform enthalten sind, können Sie auf die entsprechenden NuGet-Pakete verweisen, um diese Typen bereitzustellen.
Da die Plattformen, die Ihre App unterstützt, durch die Installation neuer Frameworks aktualisiert werden, können Sie zusätzliche Verweise entfernen.

Diese Trennung bedeutet, dass Sie neue Sprachfeatures auch dann verwenden können, wenn Sie Computer anzielen, die das entsprechende Framework nicht besitzen.
