---
title: Verweisassemblys
description: Erfahren Sie mehr über Verweisassemblys, eine spezielle Art von Assemblys in .NET, die nur die öffentliche API-Oberfläche der Bibliothek enthalten.
author: MSDN-WhiteKnight
ms.date: 09/12/2019
ms.openlocfilehash: 2f7f026c7fca4b772be85671dcc3a2a6d50a385c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831051"
---
# <a name="reference-assemblies"></a>Verweisassemblys

*Verweisassemblys*  sind eine besondere Art von Assembly, die nur die Mindestmenge an Metadaten enthalten, die zum Darstellen der öffentlichen API-Oberfläche der Bibliothek erforderlich sind. Sie beinhalten Deklarationen für alle Member, die beim Verweis auf eine Assembly in Buildtools von Bedeutung sind, schließen aber alle Memberimplementierungen und Deklarationen privater Member aus, die keine beobachtbaren Auswirkungen auf ihren API-Vertrag haben. Im Gegensatz dazu werden reguläre Assemblys als *Implementierungsassemblys* bezeichnet.

Referenzassemblys können nicht zur Ausführung geladen werden, sie können jedoch auf die gleiche Weise wie Implementierungsassemblys als Compilereingaben übergeben werden. Referenzassemblys werden in der Regel mit dem Software Development Kit (SDK) einer bestimmten Plattform oder Bibliothek verteilt.

Die Verwendung einer Verweisassembly ermöglicht Entwicklern das Erstellen von Programmen für eine bestimmte Bibliotheksversion, ohne dass die vollständige Implementierungsassembly für diese Version vorhanden ist. Angenommen, Sie haben nur die neueste Version einer Bibliothek auf Ihrem Computer, aber Sie möchten ein Programm erstellen, das auf eine frühere Version dieser Bibliothek abzielt. Wenn Sie direkt mit der Implementierungsassembly kompilieren, verwenden Sie möglicherweise versehentlich API-Member, die in der früheren Version nicht verfügbar sind. Sie finden diesen Fehler nur, wenn Sie das Programm auf dem Zielcomputer testen. Wenn Sie eine Kompilierung mit der Verweisassembly für die frühere Version ausführen, erhalten Sie sofort einen Kompilierzeitfehler.

Darüber hinaus kann eine Referenzassembly einen Vertrag darstellen, d.h. einen Satz von APIs, der nicht der konkreten Implementierungsassembly entspricht. Solche Referenzassemblys, die als *Vertragsassemblys* bezeichnet werden, können verwendet werden, um mehrere Plattformen als Ziel festzulegen, die denselben Satz von APIs unterstützen. .NET Standard stellt z.B. die Vertragsassembly *netstandard.dll* bereit, die den Satz allgemeiner APIs darstellt, die von verschiedenen .NET-Plattformen gemeinsam verwendet werden. Die Implementierungen dieser APIs sind in verschiedenen Assemblys auf unterschiedlichen Plattformen enthalten, z.B. *mscorlib.dll* für .NET Framework oder *System.Private.CoreLib.dll* für .NET Core. Eine Bibliothek für .NET Standard kann auf allen Plattformen ausgeführt werden, die .NET Standard unterstützen.

## <a name="using-reference-assemblies"></a>Verwenden von Verweisassemblys

Um bestimmte APIs aus Ihrem Projekt zu verwenden, müssen Sie Verweise auf deren Assemblys hinzufügen. Sie können Verweise sowohl zu Implementierungsassemblys als auch zu Referenzassemblys hinzufügen. Die Verwendung von Referenzassemblys wird immer empfohlen, wenn sie zur Verfügung stehen. Dadurch können Sie sicherstellen, dass Sie nur die unterstützten API-Mitglieder in der Zielversion verwenden, deren Verwendung von den API-Entwicklern geplant ist. Das Verwenden der Referenzassembly stellt sicher, dass Sie keine Abhängigkeit in Implementierungsdetails einbringen.

Verweisassemblys für .NET Framework-Bibliotheken werden mit Zielpaketen verteilt. Sie können sie abrufen, indem Sie einen eigenständigen Installer herunterladen oder eine Komponente im Visual Studio-Installer auswählen. Weitere Informationen finden Sie unter [Installieren von .NET Framework für Entwickler](../../framework/install/guide-for-developers.md). Für .NET Core und .NET Standard werden Verweisassemblys nach Bedarf automatisch heruntergeladen (über NuGet), und es wird darauf verwiesen. Für .NET Core 3.0 und höher befinden sich die Verweisassemblys für das Kernframework im Paket [Microsoft.NETCore.App.Ref](https://www.nuget.org/packages/Microsoft.NETCore.App.Ref) (das Paket [Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App) wird stattdessen für Versionen vor 3.0 verwendet).

Wenn Sie in Visual Studio über das Dialogfeld **Verweis hinzufügen** Verweise auf .NET-Framework-Assemblys hinzufügen, wählen Sie eine Assembly aus der Liste aus, und Visual Studio ermittelt automatisch Verweisassemblys, die der in Ihrem Projekt ausgewählten Zielframeworkversion entsprechen. Dasselbe gilt für das direkte Hinzufügen von Verweisen im MSBuild-Projekt mit dem Projektelement [Reference](/visualstudio/msbuild/common-msbuild-project-items#reference): Sie müssen nur den Assemblynamen angeben, nicht den vollständigen Dateipfad. Wenn Sie in der Befehlszeile Verweise auf diese Assemblys mit der Compileroption `-reference` ([in C#](../../csharp/language-reference/compiler-options/reference-compiler-option.md) und [in Visual Basic](../../visual-basic/reference/command-line-compiler/reference.md)) oder mit der Methode <xref:Microsoft.CodeAnalysis.Compilation.AddReferences%2A?displayProperty=nameWithType> in der Roslyn-API hinzufügen, müssen Sie manuell Verweisassemblydateien für die richtige Zielplattformversion angeben. .NET Framework-Verweisassemblydateien befinden sich im Verzeichnis *%ProgramFiles (x86)%\\Reference Assemblies\\Microsoft\\Framework\\.NETFramework*. Für .NET Core können Sie erzwingen, dass der Veröffentlichungsvorgang Verweisassemblys für Ihre Zielplattform in das Unterverzeichnis *publish/refs* des Ausgabeverzeichnisses kopiert, indem Sie die `PreserveCompilationContext`-Projekteigenschaft auf `true` festlegen. Anschließend können Sie diese Verweisassemblydateien an den Compiler übergeben. Die Verwendung von `DependencyContext` aus dem Paket [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/) kann helfen, ihre Pfade zu ermitteln.

Da sie keine Implementierung enthalten, können Referenzassemblys nicht zur Ausführung geladen werden. Der Versuch, sie zu laden, führt zu <xref:System.BadImageFormatException?displayProperty=nameWithType>. Wenn Sie den Inhalt einer Verweisassembly untersuchen möchten, können Sie diese in den auf Reflexion beschränkten Kontext im .NET Framework (mit der <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType>-Methode) oder in <xref:System.Reflection.MetadataLoadContext> in .NET Core laden.

## <a name="generating-reference-assemblies"></a>Generieren von Verweisassemblys

Das Generieren von Referenzassemblys für Ihre Bibliotheken kann nützlich sein, wenn Ihre Bibliotheksconsumer ihre Programme mit vielen verschiedenen Versionen der Bibliothek erstellen müssen. Die Verteilung von Implementierungsassemblys für alle diese Versionen ist aufgrund ihrer Größe möglicherweise nicht praktikabel. Referenzassemblys sind kleiner, sodass die Verteilung als Teil des SDK Ihrer Bibliothek die Downloadgröße verringert und Speicherplatz spart.

IDEs und Buildtools können ebenfalls Verweisassemblys nutzen, um Buildzeiten bei umfangreichen Lösungen zu reduzieren, die aus mehreren Klassenbibliotheken bestehen. Normalerweise wird ein Projekt in inkrementellen Buildszenarien neu erstellt, wenn eine seiner Eingabedateien geändert wird, einschließlich der Assemblys, von denen es abhängt. Die Implementierungsassembly ändert sich immer dann, wenn der Programmierer die Implementierung eines beliebigen Members ändert. Die Verweisassembly ändert sich nur, wenn ihre öffentliche API betroffen ist. Daher ermöglicht die Verwendung der Referenzassembly als Eingabedatei anstelle der Implementierungsassembly in einigen Fällen das Überspringen des Buildvorgangs des abhängigen Projekts.

Sie können Verweisassemblys folgendermaßen generieren:

- In einem MSBuild-Projekt mithilfe der [`ProduceReferenceAssembly`-Projekteigenschaft](/visualstudio/msbuild/common-msbuild-project-properties).
- Beim Kompilieren von Programmen über die Befehlszeile, indem Sie die Compileroptionen `-refonly` ([C#](../../csharp/language-reference/compiler-options/refonly-compiler-option.md) / [Visual Basic](../../visual-basic/reference/command-line-compiler/refonly-compiler-option.md)) oder `-refout` ([C#](../../csharp/language-reference/compiler-options/refout-compiler-option.md) / [Visual Basic](../../visual-basic/reference/command-line-compiler/refout-compiler-option.md)) angeben.
- Wenn Sie die Roslyn-API verwenden, legen Sie <xref:Microsoft.CodeAnalysis.Emit.EmitOptions.EmitMetadataOnly?displayProperty=nameWithType> auf `true` fest, und <xref:Microsoft.CodeAnalysis.Emit.EmitOptions.IncludePrivateMembers?displayProperty=nameWithType> auf `false` in einem Objekt, das an die <xref:Microsoft.CodeAnalysis.Compilation.Emit%2A?displayProperty=nameWithType>-Methode übergeben wird.

Wenn Sie Verweisassemblys mit NuGet-Paketen verteilen möchten, müssen Sie sie in das Unterverzeichnis *ref\\* unter dem Paketverzeichnis anstatt im das Unterverzeichnis *lib\\* einbinden, das für die Implementierungsassemblys verwendet wird.

## <a name="reference-assemblies-structure"></a>Struktur von Verweisassemblys

Verweisassemblys sind eine Erweiterung des verwandten Konzepts der *auf Metadaten beschränkten Assemblys*. Bei auf Metadaten beschränkten Assemblys werden die Methodentexte durch einen einzigen `throw null`-Text ersetzt, sie enthalten jedoch alle Member außer anonymen Typen. Der Grund für die Verwendung von `throw null`-Text (im Gegensatz zu keinem Text) besteht darin, dass **PEVerify** erfolgreich ausgeführt und übergeben werden kann (und damit die Vollständigkeit der Metadaten überprüft).

Verweisassemblys entfernen außerdem Metadaten (private Member) aus auf Metadaten beschränkten Assemblys:

- Eine Verweisassembly verfügt nur über die Verweise, die es in der API-Oberfläche benötigt. Die echte Assembly kann über zusätzliche Verweise verfügen, die sich auf bestimmte Implementierungen beziehen. Bei Instanzen verweist die Referenzassembly für `class C { private void M() { dynamic d = 1; ... } }` nicht auf Typen, die für `dynamic` erforderlich sind.
- Private Funktionsmember (Methoden, Eigenschaften und Ereignisse) werden in den Fällen entfernt, in denen ihre Entfernung sich nicht erkennbar auf die Kompilierung auswirkt. Wenn keine [InternalsVisibleTo](xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute)-Attribute vorhanden sind, werden interne Funktionsmember ebenfalls entfernt.

Die Metadaten in Referenzassemblys behalten die folgenden Informationen bei:

- Alle Typen, einschließlich privater und geschachtelter Typen.
- Alle Attribute, selbst interne.
- Alle virtuellen Methoden.
- Explizite Schnittstellenimplementierungen.
- Explizit implementierte Eigenschaften und Ereignisse, weil ihre Accessoren virtuell sind.
- Alle Felder von Strukturen.

Verweisassemblys enthalten ein [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute)-Attribut auf Assemblyebene. Dieses Attribut kann in der Quelle angegeben werden (dann muss der Compiler es nicht synthetisch erstellen). Aufgrund dieses Attribut verweigern Runtimes das Laden von Referenzassemblys für die Ausführung (sie können aber im reflektionsbezogenen Modus geladen werden).

Genaue Details der Verweisassemblystruktur hängen von der Compilerversion ab. Neuere Versionen können weitere Metadaten ausschließen, wenn festgestellt wird, dass sie sich nicht auf die öffentliche API-Oberfläche auswirken.

> [!NOTE]
> Die Informationen in diesem Abschnitt gelten nur für Verweisassemblys, die von Roslyn-Compilern ab C# Version 7.1 oder Visual Basic Version 15.3 generiert werden. Die Struktur von Verweisassemblys für .NET Framework- und .NET Core-Bibliotheken kann sich in einigen Details unterscheiden, da sie ihren eigenen Mechanismus zum Generieren von Verweisassemblys verwenden. Sie verfügen z.B. möglicherweise über vollständig leere Methodenkörper anstelle des `throw null`-Texts. Das allgemeine Prinzip gilt jedoch weiterhin: Sie verfügen nicht über verwendbare Methodenimplementierungen und enthalten Metadaten nur für Member, die eine sichtbare Auswirkung aus der Perspektive einer öffentlichen API besitzen.

## <a name="see-also"></a>Siehe auch

- [Assemblys in .NET](index.md)
- [Übersicht über Frameworkziele](/visualstudio/ide/visual-studio-multi-targeting-overview)
- [How to: Hinzufügen oder Entfernen von Verweisen mit dem Verweis-Manager](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager)
