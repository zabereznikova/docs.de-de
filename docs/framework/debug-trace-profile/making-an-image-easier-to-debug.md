---
title: Erleichtern des Debuggens für ein Abbild
ms.date: 03/30/2017
helpviewer_keywords:
- images [.NET Framework], debugging
- executable image for debugging
- debugging [.NET Framework], executable images for
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c58008bc621ea95fbb2e4cc5e7d4521576aca37c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="making-an-image-easier-to-debug"></a>Erleichtern des Debuggens für ein Abbild
Beim Kompilieren von nicht verwaltetem Code können Sie durch das Festlegen von IDE-Schaltern oder Befehlszeilenoptionen ein ausführbares Image zum Debuggen konfigurieren. Sie können beispielsweise die Befehlszeilenoption /**Zi** in Visual C++ verwenden, um zur Ausgabe von Debugsymboldateien aufzufordern (Dateierweiterung „.pdb“). Dementsprechend weist die Befehlszeilenoption /**Od** den Compiler an, die Optimierung zu deaktivieren. Der erzeugte Code wird langsamer ausgeführt, lässt sich jedoch gegebenenfalls einfacher debuggen.  
  
 Beim Kompilieren von verwaltetem Code in .NET Framework kompilieren Compiler (z. B. Visual C++, Visual Basic und C#) ihr Quellprogramm in Microsoft Intermediate Language (MSIL). Anschließend wird MSIL unmittelbar vor der Ausführung mit JIT in systemeigenen Computercode kompiliert. Ähnlich wie bei nicht verwaltetem Code können Sie durch das Festlegen von IDE-Schaltern oder Befehlszeilenoptionen ein ausführbares Abbild zum Debuggen konfigurieren. Darüber hinaus können Sie die JIT-Kompilierung zum Debuggen im Großen und Ganzen genauso konfigurieren.  
  
 Diese JIT-Konfiguration hat zwei Aspekte:  
  
-   Sie können den JIT-Compiler anweisen, Verfolgungsinformationen zu generieren. Dadurch kann der Debugger eine Kette von MSIL dem entsprechenden Computercode zuordnen und verfolgen, wo lokale Variablen und Funktionsargumente gespeichert werden.  In .NET Framework, Version 2.0, generiert der JIT-Compiler stets Verfolgungsinformationen, d. h., Sie müssen diese nicht anfordern.  
  
-   Sie können den JIT-Compiler anweisen, den erzeugten Computercode nicht zu optimieren.  
  
 Normalerweise legt der Compiler, der die MSIL generiert, diese JIT-Compileroptionen entsprechend fest. Sie basieren auf den angegebenen IDE-Schaltern oder Befehlszeilenoptionen, die Sie angeben (z.B. /**Od**).  
  
 Mitunter kann es erforderlich sein, das Verhalten des JIT-Compilers zu ändern, sodass der generierte Computercode einfacher zu debuggen ist. So können Sie z. B. JIT-Verfolgungsinformationen für eine Verkaufsversion generieren oder die Optimierung steuern. Dazu können Sie eine Initialisierungsdatei (INI) verwenden.  
  
 Beispiel: Wenn die zu debuggende Assembly MyApp.exe heißt, erstellen Sie in dem Ordner, in dem MyApp.exe gespeichert ist, eine Textdatei mit dem Namen MyApp.ini, die die folgenden drei Zeilen enthält:  
  
```  
[.NET Framework Debugging Control]  
GenerateTrackingInfo=1  
AllowOptimize=0  
```  
  
 Sie können für die Optionen jeweils den Wert 0 oder 1 einstellen. Nicht vorhandene Optionen haben standardmäßig den Wert 0. Am einfachsten lässt sich die Assembly debuggen, wenn Sie für `GenerateTrackingInfo` 1 und für `AllowOptimize` 0 festlegen.  
  
> [!NOTE]
>  In .NET Framework Version 2.0 generiert der JIT-Compiler unabhängig vom Wert für `GenerateTrackingInfo` immer Verfolgungsinformationen. Der `AllowOptimize`-Wert hat jedoch weiterhin Auswirkungen. Wenn Sie das native Image mithilfe von [Ngen.exe (Native Image Generator)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) ohne Optimierung vorkompilieren, muss bei der Ausführung von „Ngen.exe“ die INI-Datei im Zielordner mit der Einstellung `AllowOptimize=0` vorhanden sein. Falls Sie eine Assembly ohne Optimierung vorkompiliert haben, müssen Sie den vorkompilierten Code mit der **/uninstall**-Option von „Ngen.exe“ entfernen, bevor Sie „Ngen.exe“ erneut ausführen, um den Code in optimierter Form vorzukompilieren. Wenn die INI-Datei nicht im Ordner vorhanden ist, kompiliert Ngen.exe den Code standardmäßig optimiert vor.  
  
> [!NOTE]
>  <xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType> kontrolliert die Einstellungen für eine Assembly. **DebuggableAttribute** enthält zwei Felder, in denen festgelegt wird, ob der JIT-Compiler eine Optimierung durchführen und/oder Verfolgungsinformationen generieren soll. In .NET Framework, Version 2.0, generiert der JIT-Compiler immer Verfolgungsinformationen.  
  
> [!NOTE]
>  Bei Verkaufsversionen legen Compiler das Attribut **DebuggableAttribute** nicht fest. Der JIT-Compiler generiert standardmäßig Computercode, der eine optimale Leistungsfähigkeit bietet und höchst schwierig zu debuggen ist. Durch Aktivieren der JIT-Verfolgung wird die Leistung geringfügig, durch Deaktivieren der Optimierung erheblich verschlechtert.  
  
> [!NOTE]
>  **DebuggableAttribute** gilt immer für die gesamte Assembly, nicht für einzelne Module innerhalb der Assembly. Aus diesem Grund müssen Entwicklungstools benutzerdefinierte Attribute an das Metadatentoken der Assembly anfügen, sofern bereits eine Assembly erstellt wurde oder aber an die **System.Runtime.CompilerServices.AssemblyAttributesGoHere**-Klasse. Das ALink-Tool gibt diese **DebuggableAttribute**-Attribute von den einzelnen Modulen an die Assembly weiter, deren Bestandteil sie werden. Wenn hierbei ein Konflikt auftritt, schlägt der ALink-Vorgang fehl.  
  
> [!NOTE]
>  In Version 1.0 von .NET Framework fügt der Microsoft Visual C++-Compiler das **DebuggableAttribute** hinzu, wenn die Compileroptionen **/clr** und **/Zi** angegeben werden. In Version 1.1 von .NET Framework müssen Sie entweder das **DebugabbleAttribute** manuell im Code hinzufügen oder die Linkeroption **/ASSEMBLYDEBUG** verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen, Ablaufverfolgung und Profilerstellung](../../../docs/framework/debug-trace-profile/index.md)  
 [Aktivieren von JIT-attach Debugging](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)  
 [Aktivieren der Profilerstellung](http://msdn.microsoft.com/library/3b669676-f0e0-4ebf-8674-68986dd2020d)
