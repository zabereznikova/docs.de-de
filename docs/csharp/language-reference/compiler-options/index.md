---
description: C#-Compileroptionen
title: C#-Compileroptionen
ms.date: 07/20/2015
f1_keywords:
- cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
ms.openlocfilehash: bcb246055ecb553bbefad2a0d5c95bf6a083ee6f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125526"
---
# <a name="c-compiler-options"></a><span data-ttu-id="04a2f-103">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="04a2f-103">C# Compiler Options</span></span>

<span data-ttu-id="04a2f-104">Der Compiler generiert ausführbare Dateien (EXE), Dynamic Link Libraries (DLL) oder Codemodule (NETMODULE).</span><span class="sxs-lookup"><span data-stu-id="04a2f-104">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>

<span data-ttu-id="04a2f-105">Jede Compileroption ist in zwei Varianten verfügbar: **-option** und **/option**.</span><span class="sxs-lookup"><span data-stu-id="04a2f-105">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="04a2f-106">In der Dokumentation wird nur das Formular **-option** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="04a2f-106">The documentation only shows the **-option** form.</span></span>

<span data-ttu-id="04a2f-107">In Visual Studio legen Sie Compileroptionen in der Datei *web.config* fest.</span><span class="sxs-lookup"><span data-stu-id="04a2f-107">In Visual Studio, you set compiler options in the *web.config* file.</span></span> <span data-ttu-id="04a2f-108">Weitere Informationen finden Sie unter [\<compiler>Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="04a2f-108">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="04a2f-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="04a2f-109">In this section</span></span>

- <span data-ttu-id="04a2f-110">[Erstellen über die Befehlszeile mit csc.exe](command-line-building-with-csc-exe.md): Informationen zum Erstellen einer Visual C#-Anwendung über die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="04a2f-110">[Command-line Building With csc.exe](command-line-building-with-csc-exe.md) Information about building a Visual C# application from the command line.</span></span>

- <span data-ttu-id="04a2f-111">[Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile](how-to-set-environment-variables-for-the-visual-studio-command-line.md): Umfasst Schritte für die Ausführung von *vsvars32.bat* zum Ermöglichen von Befehlszeilenbuilds.</span><span class="sxs-lookup"><span data-stu-id="04a2f-111">[How to set environment variables for the Visual Studio Command Line](how-to-set-environment-variables-for-the-visual-studio-command-line.md) Provides steps for running *vsvars32.bat* to enable command-line builds.</span></span>

- <span data-ttu-id="04a2f-112">[C#-Compileroptionen nach Kategorien sortiert](listed-by-category.md): Eine nach Kategorien sortierte Liste der Compileroptionen.</span><span class="sxs-lookup"><span data-stu-id="04a2f-112">[C# Compiler Options Listed by Category](listed-by-category.md) A categorical listing of the compiler options.</span></span>

- <span data-ttu-id="04a2f-113">[C#-Compileroptionen alphabetisch sortiert](listed-alphabetically.md): Eine alphabetisch sortierte Liste der Compileroptionen.</span><span class="sxs-lookup"><span data-stu-id="04a2f-113">[C# Compiler Options Listed Alphabetically](listed-alphabetically.md) An alphabetical listing of the compiler options.</span></span>

## <a name="related-sections"></a><span data-ttu-id="04a2f-114">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="04a2f-114">Related sections</span></span>

- <span data-ttu-id="04a2f-115">[Seite "Erstellen", Projekt-Designer](/visualstudio/ide/reference/build-page-project-designer-csharp): Festlegen von Eigenschaften, die das Kompilieren, Erstellen und Debuggen des Projekts regeln.</span><span class="sxs-lookup"><span data-stu-id="04a2f-115">[Build Page, Project Designer](/visualstudio/ide/reference/build-page-project-designer-csharp) Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="04a2f-116">Enthält Informationen über benutzerdefinierte Buildschritte in Visual C#-Projekten</span><span class="sxs-lookup"><span data-stu-id="04a2f-116">Includes information about custom build steps in Visual C# projects.</span></span>

- <span data-ttu-id="04a2f-117">[Standardmäßige und benutzerdefinierte Builds](/visualstudio/ide/compiling-and-building-in-visual-studio): Informationen zu Buildtypen und Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="04a2f-117">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio) Information on build types and configurations.</span></span>

- <span data-ttu-id="04a2f-118">[Vorbereiten und Verwalten von Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio): Prozeduren zum Erstellen in der Visual Studio-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="04a2f-118">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) Procedures for building within the Visual Studio development environment.</span></span>
