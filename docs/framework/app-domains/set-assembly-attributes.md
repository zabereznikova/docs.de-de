---
title: Festlegen von Assemblyattributen | Microsoft-Dokumentation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- assembly binding, attributes
- assembly manifest, attributes
ms.assetid: 36a98a81-b5b5-4c19-912a-11f91eff7f4e
caps.latest.revision: 13
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9dd77aff85a810f462d2af77f1bfbe13b77e35dd
ms.contentlocale: de-de
ms.lasthandoff: 06/02/2017

---
# <a name="setting-assembly-attributes"></a>Festlegen von Assemblyattributen
Assemblyattribute sind Werte, die Informationen zu einer Assembly bereitstellen. Die Attribute sind in die folgenden Gruppen von Informationen unterteilt:  
  
-   Attribute für Assemblyidentitäten.  
  
-   Informationsattribute.  
  
-   Attribute für Assemblymanifeste.  
  
-   Attribute für starke Namen.  
  
## <a name="assembly-identity-attributes"></a>Attribute für Assemblyidentitäten  
 Drei Attribute bestimmen zusammen mit einem starken Namen (falls zutreffend) die Identität einer Assembly: "name", "version" und "culture". Diese Attribute bilden den vollständigen Namen der Assembly und sind erforderlich, wenn im Code auf die Assembly verwiesen wird. Mit Attributen können die Version und Kultur einer Assembly festgelegt werden. Der Compiler oder der [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) legt beim Erstellen der Assembly den Namenswert auf Grundlage der Datei fest, die das Assemblymanifest enthält.  
  
 In der folgenden Tabelle werden das version- und das culture-Attribut beschrieben.  
  
|Attribut für Assemblyidentität|Beschreibung|  
|---------------------------------|-----------------|  
|<xref:System.Reflection.AssemblyCultureAttribute>|Ein aufgelistetes Feld, das die von der Assembly unterstützte Kultur angibt. Eine Assembly kann auch eine Kulturunabhängigkeit angeben. In diesem Fall enthält sie die Ressourcen für die Standardkultur. **Hinweis**: Die Runtime behandelt jede Assembly, für die das culture-Attribut nicht auf NULL festgelegt ist, als Satellitenassembly. Solche Assemblys unterliegen den Bindungsregeln für Satellitenassemblys. Weitere Informationen finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)(Seite möglicherweise auf Englisch).|  
|<xref:System.Reflection.AssemblyFlagsAttribute>|Ein Wert, der Assemblyattribute festlegt, etwa ob die Assembly parallel ausgeführt werden kann.|  
|<xref:System.Reflection.AssemblyVersionAttribute>|Ein numerischer Wert mit dem Format *Haupt*.*Neben*.*Build*.*Revision* (z. B. 2.4.0.0). Common Language Runtime verwendet diesen Wert zum Durchführen von Bindungsvorgängen in Assemblys mit der Eigenschaft "Starker Name". **Hinweis**: Wenn das <xref:System.Reflection.AssemblyInformationalVersionAttribute>-Attribut nicht auf eine Assembly angewendet wird, wird die Versionsnummer, die vom <xref:System.Reflection.AssemblyVersionAttribute>-Attribut angegeben wird, von den Eigenschaften <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=fullName>, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=fullName> und <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=fullName> verwendet.|  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie das version- und das culture-Attribut auf eine Assembly angewendet werden.  
  
 [!code-cpp[AssemblyDelaySignAttribute#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#3)] [!code-csharp[AssemblyDelaySignAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#3)] [!code-vb[AssemblyDelaySignAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#3)]  
  
## <a name="informational-attributes"></a>Informationsattribute  
 Mit Informationsattributen können Sie zusätzliche Firmen- oder Produktinformationen für eine Assembly bereitstellen. Die folgende Tabelle beschreibt die verschiedenen Informationsattribute, die auf eine Assembly angewendet werden können.  
  
|Informationsattribut|Beschreibung|  
|-----------------------------|-----------------|  
|<xref:System.Reflection.AssemblyCompanyAttribute>|Ein Zeichenfolgenwert, der einen Firmennamen angibt.|  
|<xref:System.Reflection.AssemblyCopyrightAttribute>|Ein Zeichenfolgenwert, der Copyright-Informationen angibt.|  
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Ein Zeichenfolgenwert, der die Win32-Dateiversionsnummer angibt. Dies ist normalerweise standardmäßig die Assemblyversion.|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|Ein Zeichenfolgenwert, der Versionsinformationen angibt, die zur Laufzeit nicht verwendet werden (zum Beispiel die vollständige Produktversionsnummer). **Hinweis**: Wenn dieses Attribut auf eine Assembly angewendet wird, kann die davon angegebene Zeichenfolge zur Runtime mithilfe der <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=fullName>-Eigenschaft abgerufen werden. Diese Zeichenfolge wird auch im von den Eigenschaften <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=fullName> und <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=fullName> bereitgestellten Pfad und Registrierungsschlüssel verwendet.|  
|<xref:System.Reflection.AssemblyProductAttribute>|Ein Zeichenfolgenwert, der Produktinformationen angibt.|  
|<xref:System.Reflection.AssemblyTrademarkAttribute>|Ein Zeichenfolgenwert, der Markeninformationen angibt.|  
  
 Diese Attribute können auf der Windows-Eigenschaftenseite der Assembly angezeigt werden, oder sie können mithilfe der **/win32res** -Compileroption überschrieben werden, um Ihre eigene Win32-Ressourcendatei anzugeben.  
  
## <a name="assembly-manifest-attributes"></a>Attribute für Assemblymanifeste  
 Mit Attributen für Assemblymanifeste können Informationen im Assemblymanifest angegeben werden, einschließlich Titel, Beschreibung, Standardalias und Konfiguration. In der folgenden Tabelle werden die Attribute für Assemblymanifeste beschrieben.  
  
|Attribut für Assemblymanifeste|Beschreibung|  
|---------------------------------|-----------------|  
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Ein Zeichenfolgenwert, der die Assemblykonfiguration angibt, beispielsweise "Einzelhandel" oder "Debuggen". Dieser Wert wird zur Laufzeit nicht verwendet.|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Ein Zeichenfolgenwert, der einen Standardalias angibt, der von Assemblys mit einem Verweis verwendet werden soll. Dieser Wert stellt einen Anzeigenamen zur Verfügung, wenn der eigentliche Name der Assembly nicht angezeigt wird (zum Beispiel ein GUID-Wert). Dieser Wert kann auch als Kurzform des vollen Assemblynamens verwendet werden.|  
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Ein Zeichenfolgenwert, der eine kurze Beschreibung angibt, die Natur und Zweck der Assembly zusammenfasst.|  
|<xref:System.Reflection.AssemblyTitleAttribute>|Ein Zeichenfolgenwert, der einen Anzeigenamen für die Assembly angibt. Beispielsweise kann eine Assembly mit dem Namen "comdlg" den Titel "Microsoft Common Dialog Control" haben.|  
  
## <a name="strong-name-attributes"></a>Attribute für starke Namen  
 Sie können Attribute für starke Namen verwenden, um einen starken Namen für eine Assembly festzulegen. In der folgenden Tabelle werden die Attribute für starke Namen beschrieben.  
  
|Attribute für starke Namen|Beschreibung|  
|----------------------------|-----------------|  
|<xref:System.Reflection.AssemblyDelaySignAttribute>|Ein boolescher Wert, der angibt, dass die verzögerte Signierung verwendet wird|  
|<xref:System.Reflection.AssemblyKeyFileAttribute>|Ein Zeichenfolgenwert, der den Namen der Datei angibt, die entweder den öffentlichen Schlüssel (bei verzögerter Signierung) oder öffentliche und private Schlüssel enthält, die an den Konstruktor dieses Attributs als Parameter übergeben werden. Beachten Sie, dass der Dateiname relativ zum Pfad der Ausgabedatei ist (die .exe oder .dll) und nicht zum Pfad zur Quelldatei.|  
|<xref:System.Reflection.AssemblyKeyNameAttribute>|Zeigt den Schlüsselcontainer an, der das Schlüsselpaar enthält, das an den Konstruktor dieses Attributs als Parameter übergeben wurde.|  
  
 Das folgende Codebeispiel zeigt die Attribute, die angewendet werden, wenn mithilfe der verzögerten Signierung eine Assembly mit starkem Namen mit einer Datei des öffentlichen Schlüssels `myKey.snk`erstellt wird.  
  
 [!code-cpp[AssemblyDelaySignAttribute#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#4)] [!code-csharp[AssemblyDelaySignAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#4)] [!code-vb[AssemblyDelaySignAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)   
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)
