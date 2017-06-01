---
title: "How to: Generate Primary Interop Assemblies Using Tlbimp.exe | Microsoft Docs"
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
  - "primary interop assemblies, generating"
  - "Tlbimp.exe"
  - "Type Library Importer"
ms.assetid: 5419011c-6e57-40f6-8c65-386db8f7a651
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Generate Primary Interop Assemblies Using Tlbimp.exe
Es gibt zwei Möglichkeiten, eine primäre Interop\-Assembly zu generieren:  
  
-   Verwenden von [Tlbimp.exe \(Type Library Importer\-Tool\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), das im [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] bereitgestellt wird.  
  
     Die einfachste Möglichkeit zum Erstellen primärer Interop\-Assemblys besteht darin, [Tlbimp.exe \(Type Library Importer\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) zu verwenden.  "Tlbimp.exe" bietet die folgenden Schutzvorrichtungen:  
  
    -   Es prüft auf andere registrierte primäre Interop\-Assemblys, bevor es neue Interop\-Assemblys für irgendwelche geschachtelten Typbibliotheksverweise erstellt.  
  
    -   Es kann die primäre Interop\-Assembly nicht ausgeben, wenn Sie nicht entweder den Container oder den Dateinamen angeben, um der primären Interop\-Assembly einen starken Namen zu geben.  
  
    -   Es kann keine primäre Interop\-Assembly ausgeben, wenn Sie keine Verweise auf abhängige Assemblys angeben.  
  
    -   Es kann keine primäre Interop\-Assembly ausgeben, wenn Sie Verweise auf abhängige Assemblys hinzufügen, die keine primären Interop\-Assemblys sind.  
  
-   Manuelles Erstellen von primären Interop\-Assemblys in Quellcode, indem eine Sprache verwendet wird, die mit der Common Language Specification \(CLS\) kompatibel ist, beispielsweise C\#.  Dieser Ansatz ist hilfreich, wenn keine Typbibliothek verfügbar ist.  
  
 Sie benötigen ein kryptografisches Schlüsselpaar, um eine Assembly mit einem starken Namen zu signieren.  Ausführliche Informationen finden Sie unter [Gewusst wie: Erstellen eines öffentlichen\/privaten Schlüsselpaars](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).  
  
### So generieren Sie eine primäre Interop\-Assemblys mit "Tlbimp.exe"  
  
1.  Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
     **tlbimp** *TLBDatei*  **\/primary \/keyfile:** *Dateiname* **\/out:** *ssemblyname*  
  
     In diesem Befehl ist *TLBDatei* der Name der Datei, die die COM\-Typbibliothek enthält, *Dateiname* der Name des Containers oder der Datei, der oder die das Schlüsselpaar enthält, und *Assemblyname*  der Name der Assembly, die mit einem starken Namen signiert werden soll.  
  
 Primäre Interop\-Assemblys können nur auf andere primäre Interop\-Assemblys verweisen.  Wenn Ihre Assembly auf Typen aus einer COM\-Typbibliothek eines Drittanbieters verweist, müssen Sie eine primäre Interop\-Assembly von dem Herausgeber abrufen, bevor Sie Ihre primäre Interop\-Assembly generieren können.  Wenn Sie der Herausgeber sind, müssen Sie eine primäre Interop\-Assembly für die abhängige Typbibliothek generieren, bevor Sie die verweisende primäre Interop\-Assembly generieren.  
  
 Eine abhängige primäre Interop\-Assembly mit einer Versionsnummer, die von der der ursprünglichen Typbibliothek abweicht, kann nicht erkennt werden, wenn sie im aktuellen Verzeichnis installiert ist.  Sie müssen die abhängige primäre Interop\-Assembly in der Windows\-Registrierung registrieren oder die **\/reference**\-Option verwenden, um sicherzustellen, dass "Tlbimp.exe" die abhängige DLL finden kann.  
  
 Sie können auch mehrere Versionen einer Typbibliothek einschließen.  Anweisungen hierzu finden Sie unter [How to: Wrap Multiple Versions of Type Libraries](http://msdn.microsoft.com/de-de/79eefe04-a770-4bc3-8ea2-e90ddb8ec31f).  
  
## Beispiel  
 Im folgenden Beispiel wird die COM\-Typbibliothek `LibUtil.tlb` importiert und die Assembly `LibUtil.dll` mit einem starken Namen signiert, indem die Schlüsseldatei `CompanyA.snk` verwendet wird.  Dadurch, dass kein spezieller Namespacename angegeben ist, wird in diesem Beispiel wird der Standardnamespace, `LibUtil`, erstellt.  
  
```  
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /out:LibUtil.dll  
```  
  
 Damit ein aussagekräftigere Name \(mit der Benennungsrichtline *Herstellername*.*Bibliotheksname*\) verwendet wird, werden im folgende Beispiel die Standardnamen für die Assemblydatei und den Namespace überschrieben.  
  
```  
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /namespace:CompanyA.LibUtil /out:CompanyA.LibUtil.dll  
```  
  
 Im folgenden Beispiel wird `MyLib.tlb` importiert, in der auf `CompanyA.LibUtil.dll` verwiesen wird, und wird die Assembly `CompanyB.MyLib.dll` über die Schlüsseldatei `CompanyB.snk` mit einem starken Namen signiert.  Der Namespacename `CompanyB.MyLib` wird verwendet, um den Standardnamespacenamen zu überschreiben.  
  
```  
tlbimp MyLib.tlb /primary /keyfile:CompanyB.snk /namespace:CompanyB.MyLib /reference:CompanyA.LibUtil.dll /out:CompanyB.MyLib.dll  
```  
  
## Siehe auch  
 [How to: Register Primary Interop Assemblies](../../../docs/framework/interop/how-to-register-primary-interop-assemblies.md)