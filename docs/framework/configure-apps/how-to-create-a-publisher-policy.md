---
title: 'Gewusst wie: Erstellen einer Herausgeberrichtlinie'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 91971e4d41c3a54fa72ae73a3655dab650019676
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758125"
---
# <a name="how-to-create-a-publisher-policy"></a>Gewusst wie: Erstellen einer Herausgeberrichtlinie
Anbieter von Assemblys können der Status, Anwendungen auf eine neuere Version einer Assembly verwenden soll, indem Sie z. B. eine Herausgeberrichtlinien-Datei mit der aktualisierten Assembly. Die Herausgeberrichtliniendatei gibt Assemblyumleitung und CodeBase-Einstellungen Code und verwendet das gleiche Format wie eine Anwendungskonfigurationsdatei. Die Herausgeberrichtliniendatei wird in eine Assembly kompiliert und im globalen Assemblycache platziert.  
  
 Erstellen einer Herausgeberrichtlinie umfasst drei Schritte:  
  
1.  Erstellen Sie eine Herausgeberrichtliniendatei.  
  
2.  Erstellen Sie eine Herausgeberrichtlinienassembly.  
  
3.  Fügen Sie die Herausgeberrichtlinienassembly zum globalen Assemblycache hinzu.  
  
 Das Schema für Herausgeberrichtlinien wird beschrieben, [Umleiten von Assemblyversionen](../../../docs/framework/configure-apps/redirect-assembly-versions.md). Das folgende Beispiel zeigt einen Verleger Richtliniendatei, die eine Version der leitet `myAssembly` in eine andere.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->  
         <bindingRedirect oldVersion="1.0.0.0"  
                          newVersion="2.0.0.0"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Gewusst wie: angeben eine Codebasis finden Sie unter [angeben des Speicherortes einer Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).  
  
## <a name="creating-the-publisher-policy-assembly"></a>Erstellen der Herausgeberrichtlinienassembly  
 Verwenden der [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) die Herausgeberrichtlinienassembly zu erstellen.  
  
#### <a name="to-create-a-publisher-policy-assembly"></a>So erstellen eine Herausgeberrichtlinienassembly  
  
1.  Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:  
  
     **Al/Link:** *PublisherPolicyFile* **/out:** *PublisherPolicyAssemblyFile* **/keyfile:**  *KeyPairFile* **/Platform:** *ProcessorArchitecture*  
  
     In diesem Befehl:  
  
    -   Die *PublisherPolicyFile* Argument ist der Name des der Herausgeberrichtliniendatei.  
  
    -   Die *PublisherPolicyAssemblyFile* -Argument ist der Name der Herausgeberrichtlinienassembly an, die durch diesen Befehl entsteht. Der Dateiname der Assembly muss Folgendes Format aufweisen:  
  
         **Richtlinie.** *MajorNumber* **.** *MinorNumber* **.** *mainAssemblyName* **.dll**  
  
    -   Die *KeyPairFile* -Argument ist der Name der Datei, die das Schlüsselpaar enthält. Sie müssen die Assembly und die Herausgeberrichtlinienassembly mit dem gleichen Schlüsselpaar anmelden.  
  
    -   Die *ProcessorArchitecture* Argument identifiziert die Plattform, die auf eine Assembly prozessorspezifische.  
  
        > [!NOTE]
        >  Die Möglichkeit, eine bestimmte Prozessorarchitektur ist neu in .NET Framework, Version 2.0.  
  
     Der folgende Befehl erstellt eine Herausgeberrichtlinienassembly aufgerufen `policy.1.0.myAssembly` eine Herausgeberrichtliniendatei aufgerufen `pub.config`, weist einen starken Namen auf die Assembly mit dem Schlüsselpaar in der `sgKey.snk` Datei, und gibt an, dass die Assembly der X86 ausgerichtet ist. Architektur des Prozessors.  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     Die Herausgeberrichtlinienassembly muss die Prozessorarchitektur der Assembly übereinstimmen, die er gilt. Daher verfügt die Assembly ein <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> Wert <xref:System.Reflection.ProcessorArchitecture.MSIL>, die Herausgeberrichtlinienassembly für diese Assembly muss erstellt werden, mit `/platform:anycpu`. Geben Sie eine Separate Herausgeberrichtlinienassembly für jede prozessorspezifische Assembly.  
  
     Eine Folge von dieser Regel ist, um die Prozessorarchitektur für eine Assembly zu ändern, die Komponente Haupt- oder Nebenversion der Versionsnummer geändert werden muss, damit Sie eine neue Herausgeberrichtlinienassembly mit der richtigen Prozessorarchitektur bereitstellen können. Die alte Herausgeberrichtlinienassembly Ihre Assembly nicht verarbeitet werden, sobald die Assembly über eine andere Prozessorarchitektur aufweist.  
  
     Ein weitere Konsequenz ist, dass der Linker Version 2.0 verwendet werden kann, erstellen Sie eine Herausgeberrichtlinienassembly für eine Assembly, die mit früheren Versionen von .NET Framework kompiliert, da sie immer die Prozessorarchitektur angibt.  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Hinzufügen der Herausgeberrichtlinienassembly zum globalen Assemblycache  
 Verwenden der [Global Assembly Cache-Tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) die Herausgeberrichtlinienassembly zum globalen Assemblycache hinzufügen.  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>So fügen Sie die Herausgeberrichtlinienassembly im globalen Assemblycache hinzu  
  
1.  Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:  
  
     **Gacutil/i***PublisherPolicyAssemblyFile*   
  
     Der folgende Befehl fügt `policy.1.0.myAssembly.dll` im globalen Assemblycache.  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  Die Herausgeberrichtlinienassembly kann nicht im globalen Assemblycache hinzugefügt werden, es sei denn, die ursprünglichen Herausgeberrichtlinien-Datei im gleichen Verzeichnis wie die Assembly befindet.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Konfigurieren von Apps](../../../docs/framework/configure-apps/index.md)  
 [Konfigurieren von .NET Framework-Apps](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 [Schema für Laufzeiteinstellungen](../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../docs/framework/configure-apps/file-schema/index.md)  
 [Umleiten von Assemblyversionen](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
