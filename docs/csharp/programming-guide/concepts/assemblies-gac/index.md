---
title: Assemblys und der globale Assemblycache (C#)
ms.date: 07/20/2015
ms.assetid: 149f5ca5-5b34-4746-9542-1ae43b2d0256
ms.openlocfilehash: 07ee54fc19abecba5e8335f063277418ede80b36
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408917"
---
# <a name="assemblies-and-the-global-assembly-cache-c"></a>Assemblys und der globale Assemblycache (C#)
Assemblys bilden die Grundlage für die Bereitstellung, die Versionskontrolle, die Wiederverwendung, die Festlegung des Aktivierungsumfangs und die Sicherheitsberechtigungen für eine .NET-basierte Anwendung. Assemblys sind ausführbare Dateien (EXE-Dateien) oder DLL-Dateien und bilden die Bausteine von .NET Framework. Sie stellen der Common Language Runtime die Informationen zur Verfügung, die sie zum Erkennen der Typimplementierungen benötigt. Sie können sich eine Assembly als Sammlung von Typen und Ressourcen vorstellen, die eine logische Funktionalitätseinheit bilden und zusammenarbeiten.  
  
 Assemblys können mindestens ein Modul enthalten. Beispiel: Größere Projekte können so geplant werden, dass verschiedene unabhängige Entwickler an verschiedenen Modulen arbeiten, die schließlich alle zusammen eine einzelne Assembly erstellen. Weitere Informationen zu Modulen finden Sie im Thema [Gewusst wie: Erstellen einer Mehrfachdateiassembly](../../../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md).  
  
 Assemblys verfügen über folgende Eigenschaften:  
  
-   Assemblys werden als EXE- oder DLL-Dateien implementiert.  
  
-   Sie können eine Assembly zwischen Anwendungen teilen, indem Sie sie im globalen Assemblycache ablegen. Assemblys müssen über einen starken Namen verfügen, bevor sie dem globalen Assemblycache hinzugefügt werden können. Weitere Informationen finden Sie unter [Assemblys mit starkem Namen](../../../../../docs/framework/app-domains/strong-named-assemblies.md).  
  
-   Assemblys werden nur in den Arbeitsspeicher geladen, wenn sie erforderlich sind. Wenn sie nicht verwendet werden, werden sie nicht geladen. Dies bedeutet, dass Assemblys eine effiziente Möglichkeit zur Verwaltung von Ressourcen in größeren Projekten sein können.  
  
-   Sie können mithilfe der Reflektion programmgesteuert Informationen zu einer Assembly abrufen. Weitere Informationen finden Sie unter [Reflection (C#) (Reflexion (C#))](../../../../csharp/programming-guide/concepts/reflection.md).  
  
-   Wenn Sie eine Assembly nur zu Überprüfungszwecken laden möchten, verwenden Sie eine Methode wie z. B. <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>.  
  
## <a name="assembly-manifest"></a>Assemblymanifest  
 Innerhalb jeder Assembly gibt es ein *Assemblymanifest*. Ähnlich wie ein Inhaltsverzeichnis enthält das Assemblymanifest Folgendes:  
  
-   Die Identität der Assembly (Name und Version).  
  
-   Eine Dateitabelle, die alle anderen Dateien beschreibt, aus denen die Assembly besteht, z.B. alle weiteren Assemblys, die Sie erstellt haben, auf denen Ihre EXE- oder DLL-Datei basiert, oder sogar Bitmap- oder Infodateien.  
  
-   Eine *Assemblyverweisliste*, eine Liste aller externen Abhängigkeiten, z.B. DLL-Dateien oder andere Dateien, die Ihre Anwendung benötigt, die möglicherweise von einer anderen Person erstellt wurden. Assemblyverweise enthalten Verweise auf globale und private Objekte. Globale Objekte befinden sich im globalen Assemblycache, einem Bereich, der auch anderen Anwendungen zur Verfügung steht. Private Objekte müssen sich in einem Verzeichnis auf derselben Ebene oder unterhalb des Verzeichnisses befinden, in dem die Anwendung installiert ist.  
  
 Da Assemblys Informationen zu Inhalt, Versionsverwaltung und Abhängigkeiten enthalten, sind die Anwendungen, die Sie mit C# erstellen, nicht von Windows-Registrierungswerten abhängig, damit sie ordnungsgemäß funktionieren. Assemblys reduzieren DLL-Konflikte, verbessern die Zuverlässigkeit und vereinfachen die Bereitstellung Ihrer Anwendungen. In vielen Fällen können Sie eine .NET-basierte Anwendung einfach durch Kopieren der Dateien auf den Zielcomputer installieren.  
  
 Weitere Informationen dazu finden Sie unter [Assemblymanifest](../../../../../docs/framework/app-domains/assembly-manifest.md).  
  
## <a name="adding-a-reference-to-an-assembly"></a>Hinzufügen eines Verweises auf eine Assembly  
 Um eine Assembly zu verwenden, müssen Sie einen Verweis darauf hinzufügen. Als Nächstes verwenden Sie [using directive (die Using-Direktive)](../../../../csharp/language-reference/keywords/using-directive.md), um den Namespace der Elemente zu wählen, die Sie verwenden möchten. Sobald auf eine Assembly verwiesen wird und sie importiert wird, sind alle zugänglichen Klassen, Eigenschaften, Methoden und anderen Member ihrer Namespaces für Ihre Anwendung verfügbar, als wäre ihr Code Teil der Quelldatei.  
  
 In C# können Sie auch zwei Versionen derselben Assembly in einer einzigen Anwendung verwenden. Weitere Informationen finden Sie unter [extern-Alias](../../../../csharp/language-reference/keywords/extern-alias.md).  
  
## <a name="creating-an-assembly"></a>Erstellen einer Assembly  
 Kompilieren Sie Ihre Anwendung, indem Sie **Build** im **Build**-Menü anklicken, oder indem Sie sie durch eine Befehlszeile mithilfe des Befehlszeilencompilers erstellen. Weitere Informationen zum Erstellen von Assemblys über die Befehlszeile finden Sie unter [Command-line Building With csc.exe (Erstellen von Befehlszeilen mit „csc.exe“)](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  
  
> [!NOTE]
>  Sie erstellen eine Assembly in Visual Studio, indem Sie im Menü **Build** die Option **Build** wählen.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)  
 [Assemblys in der Common Language Runtime (CLR)](../../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [Friend-Assemblys (C#)](friend-assemblies.md)  
 [Vorgehensweise: Freigeben einer Assembly für andere Anwendungen (C#)](how-to-share-an-assembly-with-other-applications.md)  
 [Vorgehensweise: Laden und Entladen von Assemblys (C#)](how-to-load-and-unload-assemblies.md)  
 [Vorgehensweise: Bestimmen, ob eine Datei eine Assembly ist (C#)](how-to-determine-if-a-file-is-an-assembly.md)  
 [Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile (C#)](how-to-create-and-use-assemblies-using-the-command-line.md)  
 [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (C#)](walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)  
 [Walkthrough: Embedding Type Information from Microsoft Office Assemblies in Visual Studio (C#) (Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys in Visual Studio (C#))](walkthrough-embedding-type-information-from-microsoft-office-assemblies.md)
