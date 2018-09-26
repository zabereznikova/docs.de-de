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
ms.openlocfilehash: e7cac3c7e6c588a82e9dfff169ba7b7aa72c35f8
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47156506"
---
# <a name="how-to-create-a-publisher-policy"></a>Gewusst wie: Erstellen einer Herausgeberrichtlinie
Anbieter von Assemblys können angeben, dass Anwendungen auf eine neuere Version einer Assembly verwenden sollen, dazu eine Herausgeberrichtlinien-Datei mit der aktualisierten Assembly ist. Die Herausgeberrichtliniendatei gibt Assemblyumleitungen und Code-Basis-Einstellungen, und verwendet das gleiche Format wie eine Anwendungskonfigurationsdatei. Die Herausgeberrichtliniendatei ist in eine Assembly kompiliert und im globalen Assemblycache platziert.  
  
 Es gibt drei Schritte zum Erstellen einer Herausgeberrichtlinie:  
  
1.  Erstellen Sie eine Herausgeberrichtlinien-Datei.  
  
2.  Erstellen Sie eine Herausgeberrichtlinienassembly an.  
  
3.  Fügen Sie der Herausgeberrichtlinienassembly im globalen Assemblycache hinzu.  
  
 Das Schema für die Herausgeberrichtlinie wird beschrieben, [Umleiten von Assemblyversionen](../../../docs/framework/configure-apps/redirect-assembly-versions.md). Das folgende Beispiel zeigt einen Verleger Richtliniendatei, die eine Version der leitet `myAssembly` in einen anderen.  
  
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
  
#### <a name="to-create-a-publisher-policy-assembly"></a>Zum Erstellen der Herausgeberrichtlinienassembly  
  
1.  Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:  
  
     **Al/Link:** *PublisherPolicyFile* **/out:** *PublisherPolicyAssemblyFile* **/keyfile:**  *KeyPairFile* **/Platform:** *ProcessorArchitecture*  
  
     In diesem Befehl:  
  
    -   Die *PublisherPolicyFile* -Argument ist der Name der Herausgeberrichtliniendatei.  
  
    -   Die *PublisherPolicyAssemblyFile* Argument ist der Name der Herausgeberrichtlinienassembly an, die durch diesen Befehl entsteht. Der Assemblyname für die Datei muss Folgendes Format aufweisen:  
  
         **die Richtlinie.** *MajorNumber* **.** *MinorNumber* **.** *mainAssemblyName* **.dll**  
  
    -   Die *KeyPairFile* Argument ist der Name der Datei mit dem Schlüsselpaar. Sie müssen die Assembly und der Herausgeberrichtlinienassembly mit dem gleichen Schlüsselpaar anmelden.  
  
    -   Die *ProcessorArchitecture* Argument identifiziert die Plattform, die von einer Assembly macht prozessorspezifische.  
  
        > [!NOTE]
        >  Die Möglichkeit, eine bestimmte Prozessorarchitektur ist neu in .NET Framework, Version 2.0.  
  
     Der folgende Befehl erstellt eine Herausgeberrichtlinienassembly namens `policy.1.0.myAssembly` über eine Herausgeberrichtliniendatei aufgerufen `pub.config`, weist einen starken Namen der Assembly, die mit dem Schlüsselpaar in der `sgKey.snk` Datei, und gibt an, dass die Assembly der X86 ausgerichtet ist. Prozessorarchitektur.  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     Die Herausgeberrichtlinienassembly muss die Prozessorarchitektur der Assembly übereinstimmen, die er zutrifft. Daher verfügt die Assembly eine <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> Wert <xref:System.Reflection.ProcessorArchitecture.MSIL>, die Herausgeberrichtlinienassembly für diese Assembly muss erstellt werden, mit `/platform:anycpu`. Sie müssen eine Separate bereitstellen Herausgeberrichtlinienassembly für jede Assembly macht prozessorspezifische.  
  
     Diese Regel hat zur Folge, um die Prozessorarchitektur für eine Assembly zu ändern, die Haupt- oder Nebenversion-Komponente, der die Versionsnummer ändern müssen, damit Sie eine neue Herausgeberrichtlinienassembly mit die richtige Prozessorarchitektur angeben können. Die alte Herausgeberrichtlinienassembly kann nicht Ihre Assembly Dienst, sobald die Assembly über eine andere Prozessorarchitektur aufweist.  
  
     Ein weitere Konsequenz ist der Version 2.0-Linker kann nicht verwendet werden, zum Erstellen der Herausgeberrichtlinienassembly für eine Assembly kompiliert mit früheren Versionen von .NET Framework, da sie immer die Prozessorarchitektur angibt.  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Hinzufügen der Herausgeberrichtlinienassembly im globalen Assemblycache  
 Verwenden der [Global Assembly Cache-Tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) der Herausgeberrichtlinienassembly im globalen Assemblycache hinzu.  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Der Herausgeberrichtlinienassembly im globalen Assemblycache hinzu  
  
1.  Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:  
  
     **Gacutil/i***PublisherPolicyAssemblyFile*  
  
     Der folgende Befehl fügt `policy.1.0.myAssembly.dll` im globalen Assemblycache.  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  Die Herausgeberrichtlinienassembly kann nicht im globalen Assemblycache hinzugefügt werden, es sei denn, die ursprüngliche Herausgeberrichtlinien-Datei im gleichen Verzeichnis wie die Assembly befindet.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Konfigurieren von Apps](../../../docs/framework/configure-apps/index.md)  
 [Konfigurieren von .NET Framework-Apps](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 [Schema für Laufzeiteinstellungen](../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../docs/framework/configure-apps/file-schema/index.md)  
 [Umleiten von Assemblyversionen](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
