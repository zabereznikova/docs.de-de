---
title: 'Vorgehensweise: Untersuchen von Assemblyinhalten mithilfe von MetadataLoadContext'
description: Lernen Sie die Verwendung von MetadataLoadContext kennen – einer API, mit der Sie .NET-Assemblys zur Untersuchung laden können.
author: MSDN-WhiteKnight
ms.date: 03/10/2020
ms.technology: dotnet-standard
ms.openlocfilehash: a782b2db4fb62cfaedaa6768e2131bda6bec864c
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80229272"
---
# <a name="how-to-inspect-assembly-contents-using-metadataloadcontext"></a>Vorgehensweise: Untersuchen von Assemblyinhalten mithilfe von MetadataLoadContext

Mithilfe der Reflektions-API in .NET können Entwickler standardmäßig die Inhalte von Assemblys untersuchen, die im Hauptausführungskontext geladen werden. Manchmal ist es jedoch nicht möglich, eine Assembly in den Ausführungskontext zu laden – weil sie beispielsweise für eine andere Plattform oder Prozessorarchitektur kompiliert wurde, oder weil es sich um eine [Referenzassembly](reference-assemblies.md) handelt. Die <xref:System.Reflection.MetadataLoadContext?displayProperty=fullName>-API ermöglicht es Ihnen, solche Assemblys zu laden und zu untersuchen. In den <xref:System.Reflection.MetadataLoadContext> geladene Assemblys werden lediglich als Metadaten behandelt, d. h. Sie können Typen in der Assembly untersuchen, aber keinen darin enthaltenen Code ausführen. Im Gegensatz zum Hauptausführungskontext lädt der <xref:System.Reflection.MetadataLoadContext> nicht automatisch Abhängigkeiten aus dem aktuellen Verzeichnis. Stattdessen wird die benutzerdefinierte Bindungslogik aus <xref:System.Reflection.MetadataAssemblyResolver> verwendet, der an sie übergeben wird.

## <a name="prerequisites"></a>Voraussetzungen

Installieren Sie zur Verwendung von <xref:System.Reflection.MetadataLoadContext> das NuGet-Paket [System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext). Es wird in jedem .NET Standard 2.0-konformen Zielframework unterstützt, wie etwa .NET Core 2.0 oder .NET Framework 4.6.1.

## <a name="create-metadataassemblyresolver-for-metadataloadcontext"></a>Erstellen von „MetadataAssemblyResolver“ für MetadataLoadContext

Zum Erstellen des <xref:System.Reflection.MetadataLoadContext> muss eine <xref:System.Reflection.MetadataAssemblyResolver>-Instanz bereitgestellt werden. Die einfachste Möglichkeit hierzu ist die Verwendung von <xref:System.Reflection.PathAssemblyResolver>, der Assemblys aus der angegebenen Sammlung mit Assembly-Pfadzeichenfolgen auflöst. Diese Sammlung sollte neben den Assemblys, die Sie direkt untersuchen möchten, auch alle benötigten Abhängigkeiten umfassen. Um beispielsweise das custom-Attribut in einer externen Assembly zu lesen, müssen Sie diese Assembly einschließen, da ansonsten eine Ausnahme ausgelöst wird. In den meisten Fällen sollten Sie mindestens die *Kernassembly* einschließen – also die Assembly, die integrierte Systemtypen wie z. B. <xref:System.Object?displayProperty=nameWithType> enthält. Der folgende Code zeigt, wie Sie den <xref:System.Reflection.PathAssemblyResolver> mithilfe der Sammlung erstellen, die die untersuchte Assembly und die Kernassembly der aktuellen Runtime enthält:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#CoreAssembly)]

Wenn Sie Zugriff auf alle BCL-Typen benötigen, können Sie alle Runtimeassemblys in die Sammlung aufnehmen. Der folgende Code zeigt, wie Sie den <xref:System.Reflection.PathAssemblyResolver> mithilfe der Sammlung erstellen, die die untersuchte Assembly und alle Assemblys der aktuellen Runtime enthält:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#RuntimeAssemblies)]

## <a name="create-metadataloadcontext"></a>Erstellen von MetadataLoadContext

Um den <xref:System.Reflection.MetadataLoadContext> zu erstellen, rufen Sie den zugehörigen Konstruktor <xref:System.Reflection.MetadataLoadContext.%23ctor%28System.Reflection.MetadataAssemblyResolver%2CSystem.String%29> auf und übergeben den zuvor erstellten <xref:System.Reflection.MetadataAssemblyResolver> als ersten Parameter und den Namen der Kernassembly als zweiten Parameter. Sie können den Namen der Kernassembly weglassen. In diesem Fall versucht der Konstruktor, Standardnamen wie „mscorlib“, „System.Runtime“ oder „netstandard“ zu verwenden.

Nachdem Sie den Kontext erstellt haben, können Sie mithilfe von Methoden wie z. B. <xref:System.Reflection.MetadataLoadContext.LoadFromAssemblyPath%2A> Assemblys in den Kontext laden. Sie können für geladene Assemblys alle Reflektions-APIs verwenden – mit Ausnahme derjenigen, die eine Codeausführung umfassen. Die <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A>-Methode hingegen schließt eine Ausführung von Konstruktoren ein. Verwenden Sie deshalb stattdessen die <xref:System.Reflection.MemberInfo.GetCustomAttributesData%2A>-Methode, wenn Sie benutzerdefinierte Attribute im <xref:System.Reflection.MetadataLoadContext> untersuchen müssen.

Das folgende Codebeispiel erstellt <xref:System.Reflection.MetadataLoadContext>, lädt die Assembly in den Kontext und gibt Assemblyattribute in der Konsole aus:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#CreateContext)]

## <a name="example"></a>Beispiel

Ein vollständiges Codebeispiel finden Sie unter [Untersuchen von Assemblyinhalten mithilfe von MetadataLoadContext](https://docs.microsoft.com/samples/dotnet/samples/inspect-assembly-contents-using-metadataloadcontext/).
