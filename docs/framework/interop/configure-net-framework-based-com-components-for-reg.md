---
title: 'Gewusst wie: Konfigurieren von .NET Framework-basierten COM-Komponenten für die registrierungsfreie Aktivierung'
ms.date: 03/30/2017
helpviewer_keywords:
- components [.NET Framework], manifest
- application manifests [.NET Framework]
- manifests [.NET Framework]
- registration-free COM interop, configuring .NET-based components
- activation, registration-free
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
ms.openlocfilehash: dedf5ab51ab5cf9befb5bd183968388406df4e5b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181461"
---
# <a name="how-to-configure-net-framework-based-com-components-for-registration-free-activation"></a>Gewusst wie: Konfigurieren von .NET Framework-basierten COM-Komponenten für die registrierungsfreie Aktivierung
Die Aktivierung ohne Registrierung ist bei .NET Framework-Komponenten nur geringfügig schwieriger als bei COM-Komponenten. Für das Setup sind zwei Manifeste erforderlich:  
  
- COM-Anwendungen müssen über ein Win32-Anwendungsmanifest verfügen, um die verwaltete Komponente zu bestimmen.  
  
- .NET Framework-Komponenten müssen über ein Komponentenmanifest mit den zur Laufzeit erforderlichen Aktivierungsinformationen verfügen.  
  
 In diesem Thema werden das Zuordnen eines Anwendungsmanifests zu einer Anwendung, das Zuordnen eines Komponentenmanifests zu einer Komponente und das Einbetten eines Komponentenmanifests in eine Assembly beschrieben.  
  
### <a name="to-create-an-application-manifest"></a>So erstellen Sie ein Anwendungsmanifest  
  
1. Erstellen oder bearbeiten Sie mit einem XML-Editor das Anwendungsmanifest der COM-Anwendung, die mit einer oder mehreren verwalteten Komponenten interoperiert.  
  
2. Fügen Sie am Anfang der Datei den folgenden Standardheader ein:  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
     Weitere Informationen über Elemente von Manifesten und deren Attribute finden Sie unter [Anwendungsmanifeste](/windows/desktop/SbsCs/application-manifests).  
  
3. Bestimmen Sie den Besitzer des Manifests. Im folgenden Beispiel ist `myComApp`, Version 1, Besitzer der Manifestdatei.  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"
                        name="myOrganization.myDivision.myComApp"
                        version="1.0.0.0"
                        processorArchitecture="msil"
      />  
    ```  
  
4. Bestimmen Sie die abhängigen Assemblys. Im folgenden Beispiel ist `myComApp` von `myManagedComp` abhängig.  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"
                        name="myOrganization.myDivision.myComApp"
                        version="1.0.0.0"
                        processorArchitecture="x86"
                        publicKeyToken="8275b28176rcbbef"  
      />  
      <dependency>  
        <dependentAssembly>  
          <assemblyIdentity type="win32"
                        name="myOrganization.myDivision.myManagedComp"
                        version="6.0.0.0"
                        processorArchitecture="X86"
                        publicKeyToken="8275b28176rcbbef"  
          />  
        </dependentAssembly>  
      </dependency>  
    </assembly>  
    ```  
  
5. Speichern und benennen Sie die Manifestdatei. Der Name eines Anwendungsmanifests besteht aus dem Namen der ausführbaren Assembly gefolgt von der Erweiterung MANIFEST. Der Dateiname des Anwendungsmanifests für myComApp.exe lautet z. B. myComApp.exe.manifest.  
  
 Sie können ein Anwendungsmanifest im gleichen Verzeichnis wie die COM-Anwendung installieren. Sie können es aber auch der EXE-Datei der Anwendung als eine Ressource hinzufügen. Weitere Informationen finden Sie unter [About Side-by-Side Assemblies (Parallele Assemblys)](/windows/desktop/SbsCs/about-side-by-side-assemblies-).  
  
#### <a name="to-create-a-component-manifest"></a>So erstellen Sie ein Komponentenmanifest  
  
1. Erstellen Sie mit einem XML-Editor ein Komponentenmanifest, um die verwaltete Assembly zu beschreiben.  
  
2. Fügen Sie am Anfang der Datei den folgenden Standardheader ein:  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
3. Bestimmen Sie den Besitzer der Datei. Das `<assemblyIdentity>`-Element des `<dependentAssembly>`-Elements in der Anwendungsmanifestdatei muss mit dem entsprechenden Element im Komponentenmanifest übereinstimmen. Im folgenden Beispiel ist `myManagedComp`, Version 1.2.3.4, Besitzer der Manifestdatei.  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />  
    ```  
  
4. Bestimmen Sie alle Klassen in der Assembly. Verwenden Sie das `<clrClass>`-Element, um die einzelnen Klassen in der verwalteten Assembly eindeutig zu kennzeichnen. Das Element, das ein Unterelement des `<assembly>`-Elements ist, verfügt über die in der folgenden Tabelle beschriebenen Attribute.  
  
    |attribute|Beschreibung|Erforderlich|  
    |---------------|-----------------|--------------|  
    |`clsid`|Der Bezeichner, der die zu aktivierende Klasse kennzeichnet.|Ja|  
    |`description`|Eine Zeichenfolge, die Benutzer über die Komponente informiert. Der Standardwert ist eine leere Zeichenfolge.|Nein |  
    |`name`|Eine Zeichenfolge, die die verwaltete Klasse darstellt.|Ja|  
    |`progid`|Der Bezeichner für die spät gebundene Aktivierung.|Nein |  
    |`threadingModel`|Das COM-Threadingmodell. Der Standardwert ist "Both".|Nein |  
    |`runtimeVersion`|Gibt die zu verwendende Common Language Runtime-Version (CLR) an. Wenn Sie dieses Attribut nicht angeben und die CLR nicht bereits geladen ist, wird die Komponente mit der neuesten installierten CLR vor CLR-Version 4 geladen. Wenn Sie v1.0.3705, v1.1.4322 oder v2.0.50727 angeben, wird für die Version automatisch ein Rollforward auf die neueste installierte CLR-Version vor CLR-Version 4 ausgeführt (normalerweise v2.0.50727). Falls eine andere Version der CLR bereits geladen ist und die angegebene Version prozessintern parallel geladen werden kann, wird die angegebene Version geladen. Andernfalls wird die geladene CLR verwendet. Dies kann beim Laden einen Fehler verursachen.|Nein |  
    |`tlbid`|Der Bezeichner der Typbibliothek mit den Typeninformationen über die Klasse.|Nein |  
  
     Bei allen Attributtags muss die Groß- und Kleinschreibung beachtet werden. Sie können CLSIDs, ProgIDs, Threadingmodelle und die Version der Common Language Runtime ermitteln, indem Sie die exportierte Typbibliothek der Assembly mit dem OLE/COM-Objektkatalog (Oleview.exe) anzeigen.  
  
     Das folgende Komponentenmanifest identifiziert die beiden Klassen `testClass1` und `testClass2`.  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"
                        publicKeyToken="8275b28176rcbbef"  
           />  
           <clrClass  
                        clsid="{65722BE6-3449-4628-ABD3-74B6864F9739}"  
                        progid="myManagedComp.testClass1"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass1"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <clrClass  
                        clsid="{367221D6-3559-3328-ABD3-45B6825F9732}"  
                        progid="myManagedComp.testClass2"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass2"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <file name="MyManagedComp.dll">  
           </file>  
    </assembly>  
    ```  
  
5. Speichern und benennen Sie die Manifestdatei. Der Name eines Komponentenmanifests besteht aus dem Namen der Assemblybibliothek gefolgt von der Erweiterung MANIFEST. Das Manifest zu myManagedComp.dll lautet z. B. myManagedComp.manifest.  
  
 Sie müssen das Komponentenmanifest als eine Ressource in die Assembly einbetten.  
  
#### <a name="to-embed-a-component-manifest-in-a-managed-assembly"></a>So betten Sie ein Komponentenmanifest in eine verwaltete Assembly ein  
  
1. Erstellen Sie ein Ressourcenskript, das die folgende Anweisung enthält:  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     In dieser Anweisung ist `myManagedComp.manifest` der Name des einzubettenden Komponentenmanifests. Der Name der Skriptdatei für dieses Beispiel lautet `myresource.rc`.  
  
2. Kompilieren Sie das Skript mit dem Ressourcencompiler von Microsoft Windows (Rc.exe). Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:  
  
     `rc myresource.rc`  
  
     Rc.exe erstellt die Ressourcendatei `myresource.res`.  
  
3. Kompilieren Sie die Quelldatei der Assembly erneut, und geben Sie die Ressourcendatei mit der Option **/win32res** an:  
  
    `/win32res:myresource.res`  
  
     Auch hier ist `myresource.res` der Name der Ressourcendatei mit den eingebetteten Ressourcen.  
  
## <a name="see-also"></a>Weitere Informationen

- [COM-Interop ohne Registrierung](registration-free-com-interop.md)
- [Anforderungen an COM-Interop ohne Registrierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f8h7012w(v=vs.100))
- [Konfigurieren von COM-Komponenten für eine Aktivierung ohne Registrierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x65a421a(v=vs.100))
- [Registration-Free Activation of .NET-Based Components: A Walkthrough (Exemplarische Vorgehensweise: Aktivierung der .NET-basierten Komponenten ohne Registrierung)](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973915(v=msdn.10))
