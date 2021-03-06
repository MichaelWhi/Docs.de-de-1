---
title: ASP.NET Core laden/Belastungstests
author: Jeremy-Meng
description: Beschreibt verschiedene wichtige Tools und Ansätze für Auslastungstests und Belastungstests in ASP.NET Core-apps.
ms.author: riande
ms.custom: mvc
ms.date: 01/04/2019
uid: test/loadtests
ms.openlocfilehash: 08c4251059b7d9f4549ad710054d8299c4943465
ms.sourcegitcommit: 7d6019f762fc5b8cbedcd69801e8310f51a17c18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58419380"
---
# <a name="load-and-stress-testing-aspnet-core"></a>Laden und Belastungstests Testen von ASP.NET Core

Auslastungstests und Belastungstests sind wichtig, sicherzustellen, dass eine Web-app leistungsfähig ist und skalierbar. Ihre Ziele unterscheiden, obwohl sie häufig ähnliche Tests freigeben.

**Auslastungstests**: Testet, ob die app auf eine angegebene Last von Benutzern für eine bestimmte Szenario behandeln kann, und dabei trotzdem das Antwortziel. Die app wird unter normalen Bedingungen ausgeführt.

**Belastungstests**: Tests app Stabilität bei der Ausführung unter extremen Bedingungen und häufig eine längere Zeit:

* Hohe benutzerauslastung – Spitzen oder allmählich.
* Compute-Ressourcen beschränkt.

Bei hoher Belastung kann die app Wiederherstellen nach einem Fehler und zurück zum erwarteten Verhalten? Bei hoher Belastung die app ist *nicht* unter normalen Bedingungen ausgeführt.

Visual Studio 2019 ist die letzte Version von Visual Studio mit Auslastungstestfunktionen. Kunden, die Auslastungstesttools benötigen, empfehlen wir, alternative Auslastungstesttools wie Apache JMeter, Akamai CloudTest oder Blazemeter zu verwenden. Weitere Informationen finden Sie unter den [2019 Preview Release Anmerkungen zur Visual Studio](/visualstudio/releases/2019/release-notes-preview#test-tools).

Die Dienst-Auslastungstests in Azure DevOps endet in 2020. Weitere Informationen finden Sie unter [cloudbasierte Auslastungstests Service Ende ihrer Lebensdauer](https://devblogs.microsoft.com/devops/cloud-based-load-testing-service-eol/).

## <a name="visual-studio-tools"></a>Visual Studio Tools

Visual Studio ermöglicht das Erstellen, entwickeln und Debuggen von webleistungs-und Auslastungstest. Eine Option ist verfügbar, um Tests zu erstellen, durch Aufzeichnen der Aktionen im Webbrowser.

[Schnellstart: Erstellen ein auslastungstestprojekts](/visualstudio/test/quickstart-create-a-load-test-project?view=vs-2017) erstellen, konfigurieren und Ausführen eines Auslastungstests mit Visual Studio 2017 Projekte veranschaulicht.

Weitere Informationen finden Sie unter [Zusätzliche Ressourcen](#add).

Auslastungstests können in einer lokalen ausgeführt oder führen Sie in der Cloud mit Azure DevOps konfiguriert werden.

## <a name="azure-devops"></a>Azure DevOps

Auslastungstestläufe können gestartet werden, mithilfe der [Azure DevOps Testplänen](/azure/devops/test/load-test/index?view=vsts) Service.

![Azure-Angebotsseite der DevOps-Auslastungstests](./load-tests/_static/azure-devops-load-test.png)

Der Dienst unterstützt die folgenden Typen von Test-Format an:

* Visual Studio-Test – Webtest in Visual Studio erstellt.
* HTTP-Archiv-basierten Test – erfassten HTTP-Datenverkehr in das Archiv ist während der Tests wiedergegeben.
* [URL-basierter Test](/azure/devops/test/load-test/get-started-simple-cloud-load-test?view=vsts) – ermöglicht das Angeben von URLs, um den Test, Anforderungstypen, Header und Abfragezeichenfolgen zu laden. Festlegen von Parametern, z. B. Dauer ausgeführt werden, kann eine Auslastungsmuster, Anzahl der Benutzer usw., konfiguriert werden.
* [Apache JMeter](https://jmeter.apache.org/) test.

## <a name="azure-portal"></a>Azure-Portal

[Azure-Portal ermöglicht das Einrichten und Ausführen von Web-Apps, die Auslastungstests](/azure/devops/test/load-test/app-service-web-app-performance-test?view=vsts) direkt über die Registerkarte "Leistung" des App Service im Azure-Portal.

![Azure App Service in Azure-Portal](./load-tests/_static/azure-appservice-perf-test.png)

Der Test kann einen manuellen Test mit einer angegebenen URL oder eine Visual Studio-Webtest-Datei, die mehrere URLs zu testen sein.

![Neue Leistung-Testseite im Azure-Portal](./load-tests/_static/azure-appservice-perf-test-config.png)

Am Ende des Tests werden Berichte generiert, um die Leistungsmerkmale der app anzuzeigen. Beispiel-Statistiken umfassen:

* Durchschnittliche Antwortzeit
* Maximaler Durchsatz: Anforderungen pro Sekunde
* Ausführungsfehler in Prozent

## <a name="third-party-tools"></a>Drittanbieter-Tools

Die folgende Liste enthält die Drittanbieter-Web-Leistungstools mit verschiedenen Featuresätze:

* [Apache JMeter](https://jmeter.apache.org/) : Vollständige ausgewählte Sammlung von Testtools laden. Threadgebunden: benötigen Sie einen Thread pro Benutzer.
* [Ab – Apache HTTP Server Benchmark tool](https://httpd.apache.org/docs/2.4/programs/ab.html)
* [Gatling](https://gatling.io/) : Desktop-Tool mit einer grafischen Benutzeroberfläche und Test Recorder. Bieten eine bessere Leistung als JMeter.
* [Locust.io](https://locust.io/) : Nicht begrenzt von Threads.

<a name="add"></a>

## <a name="additional-resources"></a>Zusätzliche Ressourcen

[Laden Sie die Test-blogreihe](https://blogs.msdn.microsoft.com/charles_sterling/2015/06/01/load-test-series-part-i-creating-web-performance-tests-for-a-load-test/) von Charles Sterling. Vom, aber die meisten Themen sind immer noch relevant.
