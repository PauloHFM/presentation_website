+++
draft = false
date = 2026-11-18
title = "Sync Obsidian Between Desktop and Mobile with Google Drive"
description = "A free, no-fuss way to keep one Obsidian vault in sync between your computer and your phone, using Google Drive and a small sync app."
slug = "sync-obsidian-desktop-mobile-google-drive"
authors = ["paulohfm"]
tags = ["obsidian", "notes", "google-drive", "android", "macos", "productivity"]
categories = ["Productivity"]
series = []
+++

Good ideas rarely show up while you're sitting at your desk. They show up in the bus, in the kitchen, in the middle of a walk. If your notes live in [Obsidian](https://obsidian.md), you want to jot the idea down on your phone and keep working on it from your computer later.

You don't need a paid service for that. Here is a free setup that uses only **Google Drive** and one small sync app on your phone. I'll use macOS and Android in the examples.

<!--more-->

## The idea

An Obsidian *vault* is just a folder full of Markdown files. There is no database and no special server, so any tool that keeps a folder in sync across devices will do the job.

The trick is to put the vault folder **inside Google Drive** on the computer, then sync that same Drive folder to a local folder on the phone and open it with Obsidian there too:

```text
  Computer (Obsidian)    Google Drive        Phone (Obsidian)
  ┌───────────┐          ┌───────────┐       ┌───────────┐
  │  notes/   │  <────>  │  notes/   │ <───> │  notes/   │
  └───────────┘          └───────────┘       └───────────┘
        Google Drive for desktop       two-way sync app
```

> **One rule:** this is a way to *continue* your note-taking anywhere, not to edit the same note on two devices at the same time. More on that in the [gotchas](#gotchas-and-tips) below.

## Step 1: Put a folder in Google Drive

1. Install [Google Drive for desktop](https://www.google.com/drive/download/) and sign in.
2. On a Mac, open **Finder**: you'll see a **Google Drive** location in the sidebar. (On disk it lives under `~/Library/CloudStorage/GoogleDrive-<your-email>/My Drive`.)
3. Create a new folder there, for example `notes`, and put a test file inside it (a `hello.md` with a line of text is enough).

The test file is useful later: when it shows up on your phone, you know the sync works.

## Step 2: Open that folder as a vault in Obsidian

In Obsidian on the computer:

1. Open the vault switcher and click **Manage vaults…**
2. Choose **Open folder as vault** and select the `notes` folder inside Google Drive.

Pick *Open folder as vault* and not *Create new vault*. The second one creates yet another folder underneath the location you choose, and you want Obsidian to use the Drive folder exactly as it is.

## Step 3: Two-way sync on the phone

The phone needs an app that can sync a Google Drive folder with a folder on the device. On Android, **DriveSync (Sync for Google Drive)** does the job:

1. Install the app and sign in with your Google account (it's probably already on your phone, so it's usually one tap).
2. Choose the **folder in your Drive** (`notes`) and a **local folder on the phone** to sync with.
3. Set the sync direction to **both ways**.

Two-way is the important part. With a one-way setting, what you write on the phone never reaches the computer, or the other way around.

## Step 4: Open the synced folder as a vault on the phone

Install Obsidian for mobile and open the local folder that the sync app is using as a vault. You should see your test file there. Create a note on the phone, give the sync a moment, and check that it shows up on the computer. Then try the opposite direction.

If both directions work, you're done.

## Gotchas and tips

- **One device at a time.** Sync is not instant. If you edit the same note on both devices before they've synced, one version can overwrite the other or you can end up with duplicate files. A good habit: finish writing, let it sync, then switch devices.
- **Give it a moment.** Google Drive for desktop uploads in the background, and the phone app syncs on its own schedule. If a note hasn't arrived, wait a bit or trigger a manual sync in the app before assuming something is broken.
- **Keep the vault available offline.** If Google Drive for desktop is set to stream your files, the notes folder can end up as cloud-only placeholders. In Finder, right-click the folder and choose **Offline access → Available offline** so Obsidian always has real local files.
- **Mind the hidden `.obsidian` folder.** Obsidian keeps its per-vault settings in a hidden `.obsidian` folder inside the vault. Whether your settings and plugins follow you to the phone depends on how your sync app treats hidden folders, so check it after the first sync. Some community plugins are desktop-only anyway.
- **iPhone?** This guide is for Android. I haven't tried it on iOS.

## Other options

If this setup isn't for you, there are other ways to get the same result:

- **[Obsidian Sync](https://obsidian.md/sync)**, the official paid service, with end-to-end encryption and version history.
- **iCloud**, if all your devices are Apple devices.
- **Git** or **Syncthing**, if you like more control and don't mind some tinkering.

## Wrapping up

A vault is just a folder, so syncing it is just a matter of syncing a folder. Google Drive on the computer, a two-way sync app on the phone, and you can start a note anywhere and finish it somewhere else, for free.
