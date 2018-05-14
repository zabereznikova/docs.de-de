---
title: Assemblynamen
ms.date: 03/30/2017
helpviewer_keywords:
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 8f8c2c90-f15d-400e-87e7-a757e4f04d0e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e1ab9609fe6b2c1e232f188db8306fc05828285
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="assembly-names"></a>Assemblynamen
Der Name einer Assembly wird in Metadaten gespeichert und wirkt sich erheblich auf den Geltungsbereich einer Assembly aus. Zudem hat er Einfluss darauf, wie die Assembly von einer Anwendung verwendet wird. Eine Assembly mit starkem Namen hat einen vollqualifizierten Namen, der den Namen, die Kultur, den öffentlichen Schlüssel und die Versionsnummer der Assembly enthält. Dies wird häufig als Anzeigename bezeichnet. Für geladenen Assemblys kann er mit der <xref:System.Reflection.Assembly.FullName%2A>-Eigenschaft abgerufen werden.  
  
 Die Runtime verwendet diese Informationen, um nach der Assembly zu suchen und sie von anderen Assemblys mit dem gleichen Namen zu unterscheiden. Eine Assembly mit dem starken Namen `myTypes` könnte z.B. folgenden vollqualifizierten Namen haben:  
  
```  
myTypes, Version=1.0.1234.0, Culture=en-US, PublicKeyToken=b77a5c561934e089c, ProcessorArchitecture=msil  
```  
  
> [!NOTE]
>  In .NET Framework Version 2.0 wird Prozessorarchitektur zur Assemblyidentität hinzugefügt. Dies macht prozessorspezifische Assemblyversionen möglich. Sie können Versionen einer Assembly erstellen, deren Identität sich nur in der Prozessorarchitektur unterschiedet, z.B. prozessorspezifische 32-Bit- und 64-Bit-Versionen. Die Prozessorarchitektur ist für starke Namen nicht unbedingt erforderlich. Weitere Informationen finden Sie unter <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A?displayProperty=nameWithType>.  
  
 In diesem Beispiel gibt der vollqualifizierte Name an, dass die Assembly `myTypes` einen starken Namen mit einem öffentlichen Schlüsseltoken hat, den Kulturwert für Englisch (USA) und die Versionsnummer 1.0.1234.0. Seine Prozessorarchitektur ist „msil“. Das heißt, dass er in 32-Bit- oder 64-Bit-Code JIT-kompiliert (Just-In-Time) wird, je nach Betriebssystem und Prozessor.  
  
 Code, der Typen in einer Assembly anfordert, muss einen vollqualifizierten Assemblynamen verwenden. Dies wird als vollqualifizierte Bindung bezeichnet. Die Teilbindung, die nur einen Assemblynamen angibt, ist nicht zulässig, wenn auf Assemblys in .NET Framework verwiesen wird.  
  
 Alles Assemblyverweise auf Assemblys, aus denen .NET Framework besteht, müssen auch einen vollqualifizierten Namen der Assembly enthalten. Der Verweis auf die System.Data-Assembly von .NET Framework würde für Version 1.0 z.B. Folgendes enthalten:  
  
```  
System.data, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
```  
  
 Beachten Sie, dass die Version den Versionsnummern aller Assemblys von .NET Framework entspricht, die mit .NET Framework Version 1.0 geliefert wurden. Der Kulturwert von Assemblys von .NET Framework ist immer neutral, und der öffentliche Schlüssel entspricht dem im oben stehenden Beispiel gezeigten Schlüssel.  
  
 Um z.B. einen Assemblyverweis in eine Konfigurationsdatei einzufügen, um einen Ablaufverfolgungslistener einzurichten, beziehen Sie den vollqualifizierten der Systemassembly von .NET Framework mit ein:  
  
```xml  
<add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
```  
  
> [!NOTE]
>  Die Runtime beachtet bei Assemblynamen keine Groß- und Kleinschreibung, wenn sie diese an Assemblys bindet. Die im Assemblynamen verwendete Schreibweise wird aber beibehalten. Mehrere Funktionen in [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] achten bei Assemblynamen auf Groß- und Kleinschreibung. Die besten Ergebnisse erhalten Sie, wenn Sie bei Assemblynamen Groß- und Kleinschreibung beachten.  
  
## <a name="naming-application-components"></a>Namensanwendungskomponenten  
 Die Runtime achtet nicht auf den Dateinamen, wenn sie die Identität einer Assembly bestimmt. Die Assemblyidentität, die aus dem Assemblynamen, deren Version, Kultur und starkem Namen besteht, muss für die Runtime eindeutig sein.  
  
 Wenn Sie z.B. eine Assembly mit dem Namen „meineAssembly.exe“ haben, die auf eine Assembly mit dem Namen „meineAssembly.dll“ verweist, können Sie die Bindung ordnungsgemäß durchführen, indem Sie „meineAssembly.exe“ ausführen. Wenn allerdings eine andere Anwendung „meineAssembly.exe“ mit der <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=nameWithType>-Methode ausführt, gibt die Runtime an, dass „meineAssembly“ bereits geladen wurde, wenn „meineAssembly.exe“ die Bindung an „meineAssembly“ anfordert. In diesem Fall wird „meineAssembly.dll“ nicht geladen. Da „meineAssembly.exe“ nicht den angeforderten Typ enthält, wird eine <xref:System.TypeLoadException> ausgelöst.  
  
 Um dieses Problem zu vermeiden, achten Sie darauf, dass die Assemblys, aus denen Ihre Anwendung besteht, nicht denselben Assemblynamen haben. Alternativ können Sie Assemblys mit dem gleichen Namen auch in unterschiedliche Verzeichnisse platzieren.  
  
> [!NOTE]
>  Wenn Sie eine Assembly mit starkem Namen in den globalen Assemblycache einfügen, muss der Dateiname der Assembly mit dem Assemblynamen übereinstimmen (davon ausgenommen sind Erweiterungen des Dateinamen wie „.exe“ oder „.dll“). Wenn der Dateiname einer Assembly z.B. „meineAssembly.dll“ ist, muss der Assemblyname „meineAssembly“ sein. Private Assemblys, die nur im Stammanwendungsverzeichnis bereitgestellt wurden, können einen Assemblynamen haben, der sich vom Dateinamen unterscheidet.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Bestimmen des vollqualifizierten Namens einer Assembly](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 [Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)  
 [Assemblys mit starkem Namen](../../../docs/framework/app-domains/strong-named-assemblies.md)  
 [Globaler Assemblycache](../../../docs/framework/app-domains/gac.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)
