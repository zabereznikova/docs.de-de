---
title: "Assemblynamen | Microsoft Docs"
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
  - "Assemblys [.NET Framework], Namen"
  - "Namen [.NET Framework], Assemblys"
ms.assetid: 8f8c2c90-f15d-400e-87e7-a757e4f04d0e
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Assemblynamen
Der Name einer Assembly ist in den Metadaten gespeichert und wirkt sich entscheidend auf deren Gültigkeitsbereich und Verwendung durch eine Anwendung aus.  Eine Assembly mit starkem Namen verfügt über einen vollqualifizierten Namen mit Namen, Kultur, öffentlichem Schlüssel und Versionsnummer der Assembly.  Dieser Name wird häufig als Anzeigename bezeichnet. Für geladene Assemblys kann der Namen über die <xref:System.Reflection.Assembly.FullName%2A>\-Eigenschaft abgerufen werden.  
  
 Anhand dieser Informationen wird die Assembly von der Laufzeit gefunden und von anderen Assemblys mit demselben Namen unterschieden.  Eine Assembly mit starkem Namen, die den Namen `myTypes` hat, kann beispielsweise folgenden vollqualifizierten Namen besitzen:  
  
```  
myTypes, Version=1.0.1234.0, Culture=en-US, PublicKeyToken=b77a5c561934e089c, ProcessorArchitecture=msil  
```  
  
> [!NOTE]
>  In .NET Framework, Version 2.0, wurde die Assemblyidentität durch Prozessorarchitektur ergänzt, um prozessorspezifische Versionen von Assemblys zu ermöglichen.  Sie können Versionen einer Assembly erstellen, deren Identität sich nur durch die Prozessorarchitektur unterscheidet, z. B. prozessorspezifische 32\-Bit\- und 64\-Bit\-Versionen.  Die Prozessorarchitektur ist für starke Namen nicht erforderlich.  Weitere Informationen finden Sie unter <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A?displayProperty=fullName>.  
  
 Die Assembly mit starkem Namen gibt an, dass die `myTypes`\-Assembly über einen vollqualifizierten Namen mit einem öffentlichen Schlüsseltoken, den Kulturwert für Englisch \(USA\) und die Versionsnummer 1.0.1234.0 verfügt.  Ihre Prozessorarchitektur ist "msil". Dies bedeutet, dass sie je nach Betriebssystem und Prozessor in 32\-Bit\-Code oder 64\-Bit\-Code JIT\-kompiliert \(Just\-In\-Time\) wird.  
  
 Code zum Anfordern von Typen in einer Assembly muss einen vollqualifizierten Namen einer Assembly verwenden.  Dies wird als vollqualifizierte Bindung bezeichnet.  Partielles Binden, bei dem nur ein Assemblyname angegeben wird, ist zum Verweisen auf Assemblys in .NET Framework unzulässig.  
  
 Alle Verweise auf Assemblys, aus denen sich das .NET Framework zusammensetzt, müssen ebenfalls die vollqualifizierten Namen der Assemblys verwenden.  Der Verweis auf die **System.Data**\-.NET Framework\-Assembly für Version 1.0 lautet z. B. folgendermaßen:  
  
```  
  
System.data, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
  
```  
  
 Hinweis: Die Version entspricht der Versionsnummer aller .NET Framework\-Assemblys, die im Lieferumfang von .NET Framework, Version 1.0, enthalten sind.  Für .NET Framework\-Assemblys ist die Kultur stets neutral, und der öffentliche Schlüssel ist mit dem im oben genannten Beispiel identisch.  
  
 Beispiel: Wenn Sie in einer Konfigurationsdatei einen Verweis auf eine Assembly hinzufügen möchten, um einen Ablaufverfolgungslistener einzurichten, müssen Sie den vollqualifizierten Namen der .NET Framework\-Assembly des Systems angeben:  
  
```  
<add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
```  
  
> [!NOTE]
>  Die Laufzeit berücksichtigt bei der Bindung an eine Assembly keine Groß\- und Kleinschreibung von Assemblynamen, die in einem Assemblynamen verwendete Groß\- und Kleinschreibung wird jedoch beibehalten.  Mehrere Tools in [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] berücksichtigen Groß\- und Kleinschreibung in Assemblynamen.  Verwalten Sie alle Assemblynamen unter Berücksichtigung der Groß\- und Kleinschreibung, um Problemen in solchen Fällen vorzubeugen.  
  
## Benennen von Anwendungskomponenten  
 Beim Ermitteln der Identität einer Assembly durch die Common Language Runtime wird der Dateiname nicht berücksichtigt.  Die Identität einer Assembly für die Common Language Runtime umfasst Name, Version, Kultur sowie starken Namen und muss eindeutig sein.  
  
 Wenn Sie zum Beispiel über eine Assembly mit dem Namen myAssembly.exe verfügen, die auf eine Assembly mit dem Namen myAssembly.dll verweist, wird das Binden beim Ausführen von myAssembly.exe ordnungsgemäß durchgeführt.  Führt jedoch eine andere Anwendung myAssembly.exe mit der <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=fullName>\-Methode aus, interpretiert dies die Common Language Runtime so, dass "myAssembly" bereits geladen wurde, wenn myAssembly.exe eine Bindung an "myAssembly" anfordert. In diesem Fall wird **myAssembly.dll** niemals geladen.  Da myAssembly.exe den angeforderten Typ nicht enthält, tritt eine <xref:System.TypeLoadException> auf.  
  
 Stellen Sie zur Vermeidung dieses Problems sicher, dass die Assemblys, aus denen Ihre Anwendung besteht, nicht den gleichen vollständigen Namen haben, oder legen Sie Assemblys mit gleichem Namen in verschiedenen Verzeichnissen ab.  
  
> [!NOTE]
>  Wenn Sie eine Assembly mit starkem Namen im globalen Assemblycache ablegen, müssen der Dateiname der Assembly und der Assemblyname übereinstimmen \(ohne Dateinamenerweiterungen wie .exe oder .dll\).  Lautet der Dateiname einer Assembly z. B. **myAssembly.dll**, muss die Assembly den Namen **myAssembly** tragen.  Private Assemblys, die nur im Stammverzeichnis der Anwendung bereitgestellt werden, können sich in Assembly\- und Dateiname unterscheiden.  
  
## Siehe auch  
 [Gewusst wie: Bestimmen des vollqualifizierten Namens einer Assembly](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)   
 [Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)   
 [Assemblys mit starkem Namen](../../../docs/framework/app-domains/strong-named-assemblies.md)   
 [Globaler Assemblycache](../../../docs/framework/app-domains/gac.md)   
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)