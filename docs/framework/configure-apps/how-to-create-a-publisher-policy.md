---
title: "Gewusst wie: Erstellen einer Herausgeberrichtlinie | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "GAC (Globaler Assembly-Cache), Herausgeberrichtlinienassembly"
  - "Globaler Assemblycache, Herausgeberrichtlinienassembly"
  - "Herausgeberrichtlinienassembly"
  - "Herausgeberrichtliniendateien"
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Gewusst wie: Erstellen einer Herausgeberrichtlinie
Anbieter von Assemblys können bestimmen, dass Anwendungen eine neuere Assemblyversion verwenden sollen, indem sie der aktualisierten Assembly eine Herausgeberrichtliniendatei hinzufügen.  In der Herausgeberrichtliniendatei werden Assemblyumleitungen und CodeBase\-Einstellungen festgelegt. Sie hat dasselbe Format wie eine Anwendungskonfigurationsdatei.  Die Herausgeberrichtliniendatei wird in eine Assembly kompiliert und im globalen Assemblycache abgelegt.  
  
 Die Erstellung einer Herausgeberrichtlinie umfasst drei Schritte:  
  
1.  Erstellen einer Herausgeberrichtliniendatei.  
  
2.  Erstellen einer Herausgeberrichtlinienassembly.  
  
3.  Hinzufügen der Herausgeberrichtlinienassembly zum globalen Assemblycache.  
  
 Das Schema für Herausgeberrichtlinien wird unter [Umleiten von Assemblyversionen](../../../docs/framework/configure-apps/redirect-assembly-versions.md) näher erläutert.  Das folgende Beispiel enthält eine Herausgeberrichtliniendatei, durch die eine Version von `myAssembly` zu einer anderen umgeleitet wird.  
  
```  
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
  
 Unter [Festlegen des Speicherortes einer Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md) erfahren Sie, wie eine CodeBase festgelegt wird.  
  
## Erstellen der Herausgeberrichtlinienassembly  
 Verwenden Sie das [Assembly Linker\-Tool \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md), um die Herausgeberrichtlinienassembly zu erstellen.  
  
#### So erstellen Sie eine Herausgeberrichtlinienassembly  
  
1.  Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:  
  
     **al \/link:** *publisherPolicyFile* **\/out:** *publisherPolicyAssemblyFile* **\/keyfile:** *keyPairFile* **\/platform:** *processorArchitecture*  
  
     Erläuterungen zu diesem Befehl:  
  
    -   Das *publisherPolicyFile*\-Argument entspricht dem Namen der Herausgeberrichtliniendatei.  
  
    -   Das *publisherPolicyAssemblyFile*\-Argument entspricht dem Namen der Herausgeberrichtlinienassembly, die durch diesen Befehl erstellt wird.  Der Name der Assemblydatei muss folgendes Format aufweisen:  
  
         **policy.** *majorNumber* **.** *minorNumber* **.** *mainAssemblyName* **.dll**  
  
    -   Das *keyPairFile*\-Argument entspricht dem Namen der Datei, in der das Schlüsselpaar enthalten ist.  Die Assembly und die Herausgeberrichtlinienassembly müssen mit demselben Schlüsselpaar signiert werden.  
  
    -   Das *processorArchitecture*\-Argument identifiziert die von einer prozessorspezifischen Assembly verwendete Plattform.  
  
        > [!NOTE]
        >  Die Möglichkeit, eine bestimmte Prozessorarchitektur zu verwenden, ist neu in .NET Framework, Version 2.0.  
  
     Durch den folgenden Befehl wird eine Herausgeberrichtlinienassembly mit dem Namen `policy.1.0.myAssembly` aus einer Herausgeberrichtliniendatei namens `pub.config` erstellt und der Assembly mithilfe des Schlüsselpaars in der Datei `sgKey.snk` ein starker Name zugewiesen. Darüber hinaus gibt der Befehl an, dass die Assembly die x86\-Prozessorarchitektur verwendet.  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     Die Herausgeberrichtlinienassembly muss mit der Prozessorarchitektur der Assembly übereinstimmen, für die sie gilt.  Wenn die Assembly einen <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A>\-Wert von <xref:System.Reflection.ProcessorArchitecture> hat, muss die Herausgeberrichtlinienassembly mit `/platform:anycpu` erstellt werden.  Sie müssen eine separate Herausgeberrichtlinienassembly für jede prozessorspezifische Assembly bereitstellen.  
  
     Aufgrund dieser Regel müssen Sie zum Ändern der Prozessorarchitektur einer Assembly die Haupt\- oder Nebenkomponente der Versionsnummer ändern, damit Sie eine neue Herausgeberrichtlinienassembly mit der richtigen Prozessorarchitektur zur Verfügung stellen können.  Die alte Herausgeberrichtlinienassembly kann die Assembly nicht bedienen, sobald die Assembly über eine andere Prozessorarchitektur verfügt.  
  
     Des Weiteren kann der Version 2.0\-Linker nicht zum Erstellen einer Herausgeberrichtlinienassembly für eine Assembly verwendet werden, die mit früheren Versionen von .NET Framework kompiliert wurde, da immer eine Prozessorarchitektur angegeben wird.  
  
## Hinzufügen der Herausgeberrichtlinienassembly zum globalen Assemblycache  
 Verwenden Sie das [Global Assembly Cache\-Tool \(Gacutil.exe\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), um die Herausgeberrichtlinienassembly zum globalen Assemblycache hinzuzufügen.  
  
#### So fügen Sie die Herausgeberrichtlinienassembly zum globalen Assemblycache hinzu  
  
1.  Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:  
  
     **gacutil \/i**  *publisherPolicyAssemblyFile*  
  
     Durch den folgenden Befehl wird `policy.1.0.myAssembly.dll` zum globalen Assemblycache hinzugefügt.  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  Die Herausgeberrichtlinienassembly kann nur zum globalen Assemblycache hinzugefügt werden, wenn sich die ursprüngliche Herausgeberrichtliniendatei in demselben Verzeichnis wie die Assembly befindet.  
  
## Siehe auch  
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)   
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Konfigurieren von Apps](../../../docs/framework/configure-apps/index.md)   
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/de-de/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)   
 [Schema für Laufzeiteinstellungen](../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../docs/framework/configure-apps/file-schema/index.md)   
 [Umleiten von Assemblyversionen](../../../docs/framework/configure-apps/redirect-assembly-versions.md)