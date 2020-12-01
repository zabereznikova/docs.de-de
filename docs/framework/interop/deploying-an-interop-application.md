---
title: Bereitstellen einer Interop-Anwendung
description: Stellen Sie eine Interop-Anwendung bereit, die in der Regel über eine .NET-Clientassembly, Interopassemblys verschiedener COM-Typbibliotheken und registrierte COM-Komponenten verfügt.
ms.date: 03/30/2017
helpviewer_keywords:
- deploying applications [.NET Framework], interop
- strong-named assemblies, interop applications
- unsigned assemblies
- private assemblies
- exposing COM components to .NET Framework
- interoperation with unmanaged code, deploying applications
- shared assemblies
- COM interop, deploying applications
- interoperation with unmanaged code, exposing COM components
- signed assemblies
- COM interop, exposing COM components
ms.assetid: ea8a403e-ae03-4faa-9d9b-02179ec72992
ms.openlocfilehash: 2a8c94ac482bc16cb373fc694c4610ad42e8f631
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267090"
---
# <a name="deploying-an-interop-application"></a>Bereitstellen einer Interop-Anwendung

Eine Interop-Anwendung enthält üblicherweise eine .NET-Clientassembly, eine oder mehr Interopassemblys, die unterschiedliche COM-Typbibliotheken darstellen, sowie eine oder mehrere COM-Komponenten. Visual Studio und das Windows SDK stellen Tools zum Importieren und Konvertieren einer Typbibliothek in eine Interopassembly bereit, wie in [Importieren einer Typbibliothek als Assembly](importing-a-type-library-as-an-assembly.md) beschrieben. Es gibt zwei Möglichkeiten zum Bereitstellen einer Interop-Anwendung:  
  
- Wenn Sie eingebettete Interoptypen verwenden, können Sie folgende Aktionen durchführen: Ab .NET Framework 4 können Sie den Compiler anweisen, die Typinformationen aus einer Interopassembly in die ausführbare Datei einzubetten. Der Compiler bettet nur die Typinformationen ein, die Ihre Anwendung verwendet. Sie müssen die Interop-Assembly nicht mit Ihrer Anwendung bereitstellen. Dies ist das empfohlene Verfahren.  
  
- Wenn Sie Interopassemblys bereitstellen, können Sie folgende Aktionen durchführen: Sie können einen Standardverweis auf eine Interopassembly erstellen. In diesem Fall muss die Interop-Assembly mit Ihrer Anwendung bereitgestellt werden. Wenn Sie dieses Verfahren ohne eine private COM-Komponente verwenden, verweisen Sie immer auf die primäre Interop-Assembly (PIA), die vom Autor der COM-Komponente veröffentlicht wurde, die Sie in Ihren verwalteten Code einbetten möchten. Weitere Informationen zum Erstellen und Verwenden von primären Interop-Assemblys finden Sie unter [Primäre Interop-Assemblys](/previous-versions/dotnet/netframework-4.0/aax7sdch(v=vs.100)).  
  
 Wenn Sie eingebettete Interoptypen verwenden, ist die Bereitstellung einfach und unkompliziert. Sie müssen nichts weiter tun. Im weiteren Verlauf dieses Artikels, werden die Szenarios für die Bereitstellung von Interopassemblys mit der Anwendung beschrieben.  
  
## <a name="deploying-interop-assemblies"></a>Primäre Interopassemblys  

 Assemblys können starke Namen haben. Eine Assembly mit starkem Namen enthält den öffentlichen Schlüssel des Herausgebers, der eine eindeutige Identität bereitstellt. Assemblys, die mithilfe des [Type Library Importer-Tools (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) erstellt werden, können vom Herausgeber mithilfe der **/keyfile**-Option signiert werden. Sie können die signierten Assemblys im globalen Assemblycache installieren. Nicht signierte Assemblys müssen als private Assemblys auf dem Computer des Benutzers installiert werden.  
  
### <a name="private-assemblies"></a>Private Assemblys  

 Zum Installieren einer Assembly zur privaten Nutzung, müssen die ausführbare Anwendungsdatei und die Interopassembly, die importierte COM-Typen enthält, in der gleichen Verzeichnisstruktur installiert sein. Die folgende Abbildung zeigt eine unsignierte Interopassembly zur privaten Nutzung durch Client1.exe und Client2.exe, die sich in separaten Verzeichnissen befinden. Die Interopassembly, die in diesem Beispiel LOANLib.dll genannt wird, wird zweimal installiert.  
  
 ![Verzeichnisstruktur und Windows-Registrierung](./media/deploying-an-interop-application/com-private-deployment.gif "Verzeichnisstruktur- und Registrierungseinträge für eine private Bereitstellung")  
  
 Alle COM-Komponenten, die der Anwendung zugeordnet sind, müssen in der Windows-Registrierung installiert sein. Wenn Client1.exe und Client2.exe in der Abbildung auf verschiedenen Computern installiert sind, müssen Sie die COM-Komponenten auf beiden Computern registrieren.  
  
### <a name="shared-assemblies"></a>Freigegebene Assemblys  

 Assemblys, die von mehreren Anwendungen gemeinsam genutzt werden, sollten in einem zentralen Repository, das als globaler Assemblycache bezeichnet wird, installiert werden. .NET-Clients können auf dieselbe Kopie der Interopassembly zugreifen, die signiert und im globalen Assemblycache installiert ist. Weitere Informationen zum Erstellen und Verwenden von primären Interop-Assemblys finden Sie unter [Primäre Interop-Assemblys](/previous-versions/dotnet/netframework-4.0/aax7sdch(v=vs.100)).  
  
## <a name="see-also"></a>Siehe auch

- [Verfügbarmachen von COM-Komponenten für .NET Framework](exposing-com-components.md)
- [Importing a Type Library as an Assembly (Importieren einer Typbibliothek als Assembly)](importing-a-type-library-as-an-assembly.md)
- [Verwenden von COM-Typen in verwaltetem Code](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))
- [Kompilieren eines Interop-Projekts](compiling-an-interop-project.md)
