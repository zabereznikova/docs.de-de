---
title: "Gewusst wie: Erstellen eines &#246;ffentlichen/privaten Schl&#252;sselpaars | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Schlüsselpaare für Assemblys mit starkem Namen"
  - "Signieren von Assemblys"
  - "Assemblys [.NET Framework], Signierung"
  - "Kryptografische Schlüsselpaare"
  - "SNK-Dateien (Schlüsselpaardateien)"
  - "Paare aus privaten und öffentlichen Schlüsseln"
  - "SNK-Dateien"
  - "Assemblys mit starkem Namen, Schlüsselpaare"
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Erstellen eines &#246;ffentlichen/privaten Schl&#252;sselpaars
Um eine Assembly mit einem starken Namen zu signieren, benötigen Sie ein Schlüsselpaar, das aus einem öffentlichen und einem privaten Schlüssel besteht.  Dieses kryptografische Schlüsselpaar wird während der Kompilierung zum Erstellen einer Assembly mit starkem Namen verwendet.  Sie können ein Schlüsselpaar mit dem [Strong Name\-Tool \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) erstellen.  Schlüsselpaardateien haben in der Regel die Erweiterung **.snk**.  
  
> [!NOTE]
>  In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] umfassen die Projekteigenschaftenseiten für C\# und Visual Basic eine Registerkarte **Signierung**, auf der Sie auswählen können, ob vorhandene Schlüsseldateien verwendet oder neue Schlüsseldateien generiert werden sollen, ohne Sn.exe zu verwenden.  In Visual C\+\+ können Sie den Speicherort einer vorhandenen Schlüsseldatei auf der Eigenschaftenseite **Erweitert** im Abschnitt **Linker** des Abschnitts **Konfigurationseigenschaften** im Fenster **Eigenschaftenseiten** angeben.  Die Verwendung des <xref:System.Reflection.AssemblyKeyFileAttribute>\-Attributs zur Angabe eines Schlüsseldateipaares gilt ab [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] als veraltet.  
  
### So erstellen Sie ein Schlüsselpaar  
  
1.  Geben Sie an der Eingabeaufforderung folgenden Befehl ein:  
  
     **sn –k** \<*Dateiname*\>  
  
     In diesem Befehl bezeichnet *Dateiname* den Namen der Ausgabedatei, die das Schlüsselpaar enthält.  
  
 Im folgenden Beispiel wird ein Schlüsselpaar mit dem Namen `sgKey.snk` erstellt.  
  
```  
sn -k sgKey.snk  
```  
  
 Wenn Sie eine Assembly verzögert signieren möchten und beide Schlüssel kontrollieren \(was außer in Testszenarien kaum vorkommt\), können Sie die folgenden Befehle verwenden, um ein Schlüsselpaar zu generieren, und daraus anschließend den öffentlichen Schlüssel in eine separate Datei extrahieren.  Erstellen Sie zuerst das Schlüsselpaar:  
  
```  
sn -k keypair.snk  
```  
  
-   Extrahieren Sie anschließend den öffentlichen Schlüssel aus dem Schlüsselpaar, und kopieren Sie ihn dann in eine separate Datei:  
  
```  
sn -p keypair.snk public.snk  
```  
  
-   Nachdem Sie das Schlüsselpaar erstellt haben, müssen Sie die Datei so ablegen, dass die Tools zur Signierung mit starkem Namen Zugriff darauf haben.  
  
 Beim Signieren einer Assembly mit einem starken Namen sucht das [Assembly Linker\-Tool \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md) nach der Schlüsseldatei relativ zum aktuellen und zum Ausgabeverzeichnis.  Wenn Sie einen Befehlszeilencompiler verwenden, können Sie den Schlüssel einfach in das aktuelle Verzeichnis kopieren, das die Codemodule enthält.  
  
 Wenn Sie eine frühere Version von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] verwenden, die in den Projekteigenschaften keine Registerkarte **Signierung** aufweist, sollten Sie die Schlüsseldatei im Projektverzeichnis speichern und das Dateiattribut wie folgt festlegen:  
  
 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]  
  
## Siehe auch  
 [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)