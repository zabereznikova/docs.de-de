---
title: "Verz&#246;gertes Signieren einer Assembly | Microsoft Docs"
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
  - "Verzögern der Assemblysignierung"
  - "Signieren von Assemblys"
  - "Assemblys [.NET Framework], Signieren"
  - "Assemblys mit starken Namen, Verzögern der Assemblysignierung"
  - "Teilweises Signieren von Assemblys"
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Verz&#246;gertes Signieren einer Assembly
Ein Unternehmen kann über ein streng bewachtes Schlüsselpaar verfügen, auf das nicht einmal Entwickler täglich zugreifen können.  Der öffentliche Schlüssel ist häufig frei zugänglich, der private Schlüssel hingegen ist nur einigen ausgewählten Personen bekannt.  Bei der Entwicklung von Assemblys mit starkem Namen enthält jede Assembly, die auf die Zielassembly mit starkem Namen verweist, das Token des öffentlichen Schlüssels, mit dessen Hilfe der Zielassembly ein starker Name zugewiesen wurde.  Aus diesem Grund ist es erforderlich, dass der öffentliche Schlüssel während des Entwicklungsprozesses allgemein zugänglich ist.  
  
 Sie können verzögertes oder teilweises Signieren während des Erstellens verwenden, um in der PE \(Portable Executable\)\-Datei Platz für die starke Namenssignatur zu reservieren. Das tatsächliche Signieren können Sie auf einen späteren Zeitpunkt \(normalerweise unmittelbar vor der Bereitstellung der Assembly\) verschieben.  
  
 In den folgenden Schritten wird der prinzipielle Ablauf des verzögerten Signierens einer Assembly beschrieben:  
  
1.  Besorgen Sie sich von der Organisation, die das eigentliche Signieren vornimmt, den öffentlichen Schlüssel des Schlüsselpaares.  Im Normalfall liegt dieser Schlüssel als SNK\-Datei vor, die mit dem [Strong Name\-Tool \(Sn.exe\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) erstellt werden kann, das von [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] zur Verfügung gestellt wird.  
  
2.  Fügen Sie dem Quellcode für die Assembly zwei benutzerdefinierte Attribute aus <xref:System.Reflection> hinzu:  
  
    -   <xref:System.Reflection.AssemblyKeyFileAttribute>, das den Namen der Datei, die den öffentlichen Schlüssel enthält, als Parameter an seinen Konstruktor übergibt.  
  
    -   <xref:System.Reflection.AssemblyDelaySignAttribute>, das die Verwendung von verzögertem Signieren angibt, indem es **true** als Parameter an seinen Konstruktor übergibt.  Beispiel:  
  
         [!code-cpp[AssemblyDelaySignAttribute#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#4)]
         [!code-csharp[AssemblyDelaySignAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#4)]
         [!code-vb[AssemblyDelaySignAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#4)]  
  
3.  Der Compiler fügt den öffentlichen Schlüssel in das Assemblymanifest ein und reserviert in der PE\-Datei Platz für die vollständige starke Namenssignatur.  Der echte öffentliche Schlüssel muss während der Erstellung der Assembly gespeichert werden, damit andere Assemblys, die auf diese verweisen, auf den Schlüssel zugreifen und ihn in ihrem eigenen Assemblyverweis speichern können.  
  
4.  Da die Assembly über keine gültige starke Namenssignatur verfügt, muss die Überprüfung dieser Signatur deaktiviert werden.  Diese Deaktivierung können Sie vornehmen, indem Sie die Option **–Vr** zusammen mit dem Strong Name\-Tool verwenden.  
  
     Im folgenden Beispiel wird die Überprüfung für eine Assembly mit dem Namen `myAssembly.dll` deaktiviert.  
  
    ```  
    sn –Vr myAssembly.dll  
    ```  
  
     So Überprüfung auf Plattformen deaktivieren, in denen Sie das Strong Name\-Tool, wie die RISC\-Computer \(arm\)\- Mikroprozessoren nicht ausführen können, verwenden Sie die **–Vk** \- Option, eine Registrierungsdatei zu erstellen.  Importieren Sie die ADDIN\-XML\-Registrierungsdatei in die Registrierung auf dem Computer, auf dem Sie Überprüfung ausschalten möchten.  Das folgende Beispiel erstellt eine Registrierungsdatei für `myAssembly.dll`.  
  
    ```  
    sn –Vk myRegFile.reg myAssembly.dll  
    ```  
  
     entweder mit **–Vr** oder **–Vk** \- Option können Sie eine SNK\-Datei für Testschlüsselsignierung optional einschließen.  
  
    > [!CAUTION]
    >  Verwenden Sie die Option **\-Vr** oder **–Vk** nur bei der Entwicklung.  Das Überspringen der Überprüfung einer Assembly kann ein erhebliches Sicherheitsrisiko darstellen.  Wenn die Überprüfung einer Assembly übersprungen wird, besteht die Gefahr, dass deren vollständig angegebener Assemblyname \(Assemblyname, Version, Kultur und öffentliches Schlüsseltoken\) als falsche Identität einer böswilligen Assembly verwendet wird.  Dadurch würde auch die Überprüfung der böswilligen Assembly übersprungen.  
  
    > [!NOTE]
    >  Wenn Sie während der Entwicklung mit Visual Studio auf einem 64\-Bit\-Computer verzögertes Signieren verwenden und eine Assembly für **Any CPU** kompilieren, müssen Sie die **\-Vr**\-Option möglicherweise zweimal anwenden. \(In Visual Studio ist **Any CPU** ein Wert der Buildeigenschaft **Zielplattform**. Wenn Sie die Kompilierung in der Befehlszeile vornehmen, ist dies der Standard.\) Um die Anwendung in der Befehlszeile oder von Datei vom Explorer auszuführen, verwenden Sie die 64\-Bit\-Version [Sn.exe \(Strong Name Tool\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) die Option **\-Vr** auf die Assembly anzuwenden.  Um die Assembly zur Entwurfszeit in Visual Studio zu laden \(z. B., wenn die Assembly Komponenten enthält, die von anderen Assemblys in der Anwendung verwendet werden\), verwenden Sie die 32\-Bit\-Version des Strong Name\-Tools.  Der Grund dafür besteht darin, dass der JIT \(Just\-In\-Time\)\-Compiler die Assembly bei deren Ausführung in der Befehlszeile zu systemeigenem 64\-Bit\-Code kompiliert, aber zu systemeigenem 32\-Bit\-Code, wenn die Assembly in die Entwurfszeitumgebung geladen wird.  
  
5.  Zu einem späteren Zeitpunkt \(üblicherweise unmittelbar vor der Veröffentlichung des Produkts\) übergeben Sie unter Verwendung der Option **–R** zusammen mit dem Strong Name\-Tool die Assembly der Signierungsstelle Ihrer Organisation, wo dann die eigentliche Signierung mit einem starken Namen erfolgt.  
  
     Im folgenden Beispiel wird die Assembly `myAssembly.dll` unter Verwendung des Schlüsselpaares `sgKey.snk` mit einem starken Namen signiert.  
  
    ```  
    sn -R myAssembly.dll sgKey.snk  
    ```  
  
## Siehe auch  
 [Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)   
 [Gewusst wie: Erstellen eines öffentlichen\/privaten Schlüsselpaars](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)   
 [Sn.exe \(Strong Name Tool\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)   
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)