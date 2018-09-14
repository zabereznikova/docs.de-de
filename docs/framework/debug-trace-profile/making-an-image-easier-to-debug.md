---
title: Erleichtern das Debuggen in .NET ein Abbild
description: Erfahren Sie, wie Sie ein ausführbares Image zu konfigurieren, für ein einfacheres Debuggen mithilfe von IDE wechselt und Befehlszeilenoptionen.
ms.date: 08/30/2018
helpviewer_keywords:
- images [.NET Framework], debugging
- executable image for debugging
- debugging [.NET Framework], executable images for
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f25eaaa17d4c4bd2e9522591bb0fd66445cdb6f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45610062"
---
# <a name="making-an-image-easier-to-debug-in-net"></a>Erleichtern das Debuggen in .NET ein Abbild

Beim Kompilieren von nicht verwaltetem Code können Sie durch das Festlegen von IDE-Schaltern oder Befehlszeilenoptionen ein ausführbares Image zum Debuggen konfigurieren. Sie können beispielsweise die Befehlszeilenoption /**Zi** in Visual C++ verwenden, um zur Ausgabe von Debugsymboldateien aufzufordern (Dateierweiterung „.pdb“). Dementsprechend weist die Befehlszeilenoption /**Od** den Compiler an, die Optimierung zu deaktivieren. Der resultierende Code wird langsamer ausgeführt, aber es ist einfacher zu debuggen, dies erforderlich sein sollte.

Beim Kompilieren der .NET Framework Code verwalteten kompilieren Compiler wie Visual C++, Visual Basic und C#-ihr Quellprogramm in Microsoft intermediate Language (MSIL) an. MSIL erfolgt die JIT-kompiliert, unmittelbar vor der Ausführung in systemeigenen Computercode. Ähnlich wie bei nicht verwaltetem Code können Sie durch das Festlegen von IDE-Schaltern oder Befehlszeilenoptionen ein ausführbares Image zum Debuggen konfigurieren. Sie können auch die JIT-Kompilierung zum Debuggen in die gleiche Weise konfigurieren.

Diese JIT-Konfiguration hat zwei Aspekte:

- Sie können den JIT-Compiler zum Generieren von Nachverfolgungsinformationen anfordern. Dadurch kann der Debugger eine Kette von MSIL dem entsprechenden Computercode zuordnen und verfolgen, wo lokale Variablen und Funktionsargumente gespeichert werden. Ab .NET Framework, Version 2.0, generiert der JIT-Compiler immer Überwachungsinformationen, daher keine Notwendigkeit besteht, die Anforderung.

- Sie können anfordern, dass den JIT-Compiler, um den erzeugten Computercode nicht zu optimieren.

Normalerweise legt der Compiler, der die MSIL generiert, diese JIT-Compileroptionen entsprechend basierend auf den IDE-Schaltern oder Befehlszeilenoptionen, die Sie, z. B. angeben /**Od**.

Mitunter kann es erforderlich sein, das Verhalten des JIT-Compilers zu ändern, sodass der generierte Computercode einfacher zu debuggen ist. So können Sie z. B. JIT-Verfolgungsinformationen für eine Verkaufsversion generieren oder die Optimierung steuern. Dazu können Sie eine Initialisierungsdatei (INI) verwenden.

Z. B. wenn die Assembly, die Sie debuggen möchten spricht *MyApp.exe*, anschließend können Sie eine Textdatei namens erstellen *MyApp.ini*, im gleichen Ordner wie *MyApp.exe*, enthält Diese drei Zeilen:

```txt
[.NET Framework Debugging Control]
GenerateTrackingInfo=1
AllowOptimize=0
```

Sie können für die Optionen jeweils den Wert 0 oder 1 einstellen. Nicht vorhandene Optionen haben standardmäßig den Wert 0. Am einfachsten lässt sich die Assembly debuggen, wenn Sie für `GenerateTrackingInfo` 1 und für `AllowOptimize` 0 festlegen.

Ab .NET Framework, Version 2.0, generiert der JIT-Compiler immer Verfolgungsinformationen unabhängig vom Wert für `GenerateTrackingInfo`, aber die `AllowOptimize` Wert immer noch wirkt sich ein. Wenn Sie das native Image mithilfe von [Ngen.exe (Native Image Generator)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) ohne Optimierung vorkompilieren, muss bei der Ausführung von „Ngen.exe“ die INI-Datei im Zielordner mit der Einstellung `AllowOptimize=0` vorhanden sein. Wenn Sie eine Assembly ohne Optimierung vorkompiliert haben, müssen Sie den vorkompilierten Code mit NGen.exe entfernen **/ uninstall** Option vor der Ngen.exe erneut ausführen, um den Code in optimierter Form vorzukompilieren. Wenn die INI-Datei nicht im Ordner vorhanden ist, führt die Vorkompilierung standardmäßig Ngen.exe des Codes wie optimiert.

<xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType> kontrolliert die Einstellungen für eine Assembly. **DebuggableAttribute** enthält zwei Felder, die steuern, ob der JIT-Compiler eine Optimierung und/oder Verfolgungsinformationen generieren soll. Ab .NET Framework, Version 2.0, generiert der JIT-Compiler immer Verfolgungsinformationen.

Für eine Verkaufsversion Compiler nicht legen **DebuggableAttribute**. Standardmäßig generiert der JIT-Compiler die höchste Leistung, die am schwersten zu debuggen. Durch Aktivieren der JIT-Verfolgung wird die Leistung geringfügig, durch Deaktivieren der Optimierung erheblich verschlechtert.

**DebuggableAttribute** gilt immer für die gesamte Assembly, nicht für einzelne Module innerhalb der Assembly. Aus diesem Grund müssen Entwicklungstools benutzerdefinierte Attribute an das Metadatentoken der Assembly anfügen, sofern bereits eine Assembly erstellt wurde oder aber an die **System.Runtime.CompilerServices.AssemblyAttributesGoHere**-Klasse. Das ALink-Tool stuft dann diese **DebuggableAttribute** -Attribute von den einzelnen Modulen an die Assembly werden sie Teil. Wenn ein Konflikt vorliegt, schlägt der ALink-Vorgang fehl.

> [!NOTE]
> In Version 1.0 von .NET Framework fügt der Microsoft Visual C++-Compiler das **DebuggableAttribute** hinzu, wenn die Compileroptionen **/clr** und **/Zi** angegeben werden. In Version 1.1 von .NET Framework müssen Sie entweder das **DebugabbleAttribute** manuell im Code hinzufügen oder die Linkeroption **/ASSEMBLYDEBUG** verwenden.

## <a name="see-also"></a>Siehe auch

- [Debuggen, Ablaufverfolgung und Profilerstellung](../../../docs/framework/debug-trace-profile/index.md)
- [Aktivieren von JIT-attach Debugging](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)
- [Aktivieren der Profilerstellung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s5ec0es1(v=vs.100))
