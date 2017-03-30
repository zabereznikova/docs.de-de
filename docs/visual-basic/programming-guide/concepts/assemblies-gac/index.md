---
title: Assemblys und der globale Assemblycache (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: fcf78ff1-f1ab-4a5d-b6d8-00d2046b6c80
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0b712132becfe47d50d1c06c0e8fd9940b8035e9
ms.lasthandoff: 03/13/2017

---
# <a name="assemblies-and-the-global-assembly-cache-visual-basic"></a>Assemblys und der globale Assemblycache (Visual Basic)
Assemblys bilden die Grundlage für die Bereitstellung, die Versionskontrolle, die Wiederverwendung, die Festlegung des Aktivierungsumfangs und die Sicherheitsberechtigungen für eine .NET-basierte Anwendung. Assemblys sind ausführbare Dateien (EXE-Dateien) oder DLL-Dateien und bilden die Bausteine von .NET Framework. Sie stellen der Common Language Runtime die Informationen zur Verfügung, die sie zum Erkennen der Typimplementierungen benötigt. Sie können sich eine Assembly als Sammlung von Typen und Ressourcen vorstellen, die eine logische Funktionalitätseinheit bilden und zusammenarbeiten.  
  
 Assemblys können mindestens ein Modul enthalten. Beispiel: Größere Projekte können so geplant werden, dass verschiedene unabhängige Entwickler an verschiedenen Modulen arbeiten, die schließlich alle zusammen eine einzelne Assembly erstellen. Weitere Informationen zu Modulen finden Sie im Thema [Gewusst wie: Erstellen einer Mehrfachdateiassembly](https://msdn.microsoft.com/library/226t7yxe).  
  
 Assemblys verfügen über folgende Eigenschaften:  
  
-   Assemblys werden als EXE- oder DLL-Dateien implementiert.  
  
-   Sie können eine Assembly zwischen Anwendungen teilen, indem Sie sie im globalen Assemblycache ablegen. Assemblys müssen über einen starken Namen verfügen, bevor sie dem globalen Assemblycache hinzugefügt werden können. Weitere Informationen finden Sie unter [Assemblys mit starkem Namen](https://msdn.microsoft.com/library/wd40t7ad).  
  
-   Assemblys werden nur in den Arbeitsspeicher geladen, wenn sie erforderlich sind. Wenn sie nicht verwendet werden, werden sie nicht geladen. Dies bedeutet, dass Assemblys eine effiziente Möglichkeit zur Verwaltung von Ressourcen in größeren Projekten sein können.  
  
-   Sie können mithilfe der Reflektion programmgesteuert Informationen zu einer Assembly abrufen. Weitere Informationen finden Sie unter [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md).  
  
-   Wenn Sie eine Assembly lediglich zu Überprüfungszwecken laden möchten, verwenden Sie eine Methode wie „<xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>“.  
  
## <a name="assembly-manifest"></a>Assemblymanifest  
 Jede Assembly enthält ein *Assemblymanifest*. Ähnlich wie ein Inhaltsverzeichnis enthält das Assemblymanifest Folgendes:  
  
-   Die Identität der Assembly (Name und Version).  
  
-   Eine Dateitabelle, die alle anderen Dateien beschreibt, aus denen die Assembly besteht, z.B. alle weiteren Assemblys, die Sie erstellt haben, auf denen Ihre EXE- oder DLL-Datei basiert, oder sogar Bitmap- oder Infodateien.  
  
-   Eine *Assemblyverweisliste*, eine Liste aller externen Abhängigkeiten, z.B. DLL-Dateien oder andere Dateien, die Ihre Anwendung benötigt, die möglicherweise von einer anderen Person erstellt wurden. Assemblyverweise enthalten Verweise auf globale und private Objekte. Globale Objekte befinden sich im globalen Assemblycache, einem Bereich, der auch anderen Anwendungen zur Verfügung steht, wie etwa das System32-Verzeichnis. Der <xref:Microsoft.VisualBasic?displayProperty=fullName>-Namespace ist ein Beispiel für eine Assembly im globalen Assemblycache. Private Objekte müssen sich in einem Verzeichnis auf derselben Ebene oder unterhalb des Verzeichnisses befinden, in dem die Anwendung installiert ist.  
  
 Da Assemblys Informationen zu Inhalt, Versionsverwaltung und Abhängigkeiten enthalten, sind die Anwendungen, die Sie mit Visual Basic erstellen, nicht von Windows-Registrierungswerten abhängig, damit sie ordnungsgemäß funktionieren. Assemblys reduzieren DLL-Konflikte, verbessern die Zuverlässigkeit und vereinfachen die Bereitstellung Ihrer Anwendungen. In vielen Fällen können Sie eine .NET-basierte Anwendung einfach durch Kopieren der Dateien auf den Zielcomputer installieren.  
  
 Weitere Informationen dazu finden Sie unter [Assemblymanifest](https://msdn.microsoft.com/library/1w45z383).  
  
## <a name="adding-a-reference-to-an-assembly"></a>Hinzufügen eines Verweises auf eine Assembly  
 Um eine Assembly zu verwenden, müssen Sie einen Verweis darauf hinzufügen. Als Nächstes verwenden Sie die [Imports-Anweisung](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md), um den Namespace der Elemente zu wählen, die Sie verwenden möchten. Sobald auf eine Assembly verwiesen wird und sie importiert wird, sind alle zugänglichen Klassen, Eigenschaften, Methoden und anderen Member ihrer Namespaces für Ihre Anwendung verfügbar, als wäre ihr Code Teil der Quelldatei.  
  
## <a name="creating-an-assembly"></a>Erstellen einer Assembly  
 Kompilieren Sie Ihre Anwendung durch Erstellen über die Befehlszeile mit dem Befehlszeilencompiler. Weitere Informationen zum Erstellen von Assemblys über die Befehlszeile finden Sie unter [Erstellen von der Befehlszeile aus](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
> [!NOTE]
>  Sie erstellen eine Assembly in Visual Studio, indem Sie im Menü **Build** die Option **Build** wählen.  
  
## <a name="see-also"></a>Siehe auch  
 [Assemblys in der Common Language Runtime (CLR)](https://msdn.microsoft.com/library/k3677y81)   
 [Friend-Assemblys (Visual Basic)](friend-assemblies.md)   
 [How to: Share an Assembly with Other Applications (Visual Basic)](how-to-share-an-assembly-with-other-applications.md)  (Gewusst wie: Freigeben einer Assembly für andere Anwendungen (Visual Basic))  
 [How to: Load and Unload Assemblies (Visual Basic)](how-to-load-and-unload-assemblies.md)  (Gewusst wie: Laden und Entladen von Assemblys (Visual Basic))  
 [How to: Determine If a File Is an Assembly (Visual Basic)](how-to-determine-if-a-file-is-an-assembly.md)  (Gewusst wie: Bestimmen, ob eine Datei eine Assembly ist (Visual Basic))  
 [How to: Create and Use Assemblies Using the Command Line (Visual Basic)](how-to-create-and-use-assemblies-using-the-command-line.md)  (Gewusst wie: Erstellen und Verwenden von Assemblys über die Befehlszeile (Visual Basic))  
 [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (Visual Basic)](walkthrough-embedding-types-from-managed-assemblies-in-vs.md)   
 [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys in Visual Studio (Visual Basic)](walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-vs.md)
