# TiddlyWiki MultiWikiServer Installation Repository

## Introduction

This repository contains a JavaScript package containing TiddlyWiki's [MultiWikiServer plugin](https://github.com/TiddlyWiki/TiddlyWiki5/pull/7915) that can be installed with [npm](https://www.npmjs.com/).

## Quick Start

See https://mws.tiddlywiki.com/ for full installation instructions.

```
mkdir my-mws-installation
cd  my-mws-installation
npm install TiddlyWiki/MWS
```

# Technical Rationale

MWS is a component of TiddlyWiki, and so at first sight it might not seem necessary for this repository to exist: everything needed to use MWS can be found within the main TiddlyWiki5 repository.

However, the problem is that MWS requires npm dependencies. At the moment, MWS is in its own development branch and so we've been able to modify the repository `package.json` to include the required dependencies. When MWS is eventually released and merged into the main branch of ~TiddlyWiki it will no longer be possible to include the dependencies in `package.json` because those dependencies are only needed when using MWS. It would not be acceptable for the plain, single file edition of ~TiddlyWiki to have unnecessary dependencies in `package.json`.

So, this repository exists in order to allow users to install MWS and its dependencies with a single `npm install` command, substantially simplifying the installation process.
