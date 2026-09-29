<p align="center">
   <img src="https://scoresaber.com/ScoreSaber-iOS-Default-1024x1024@1x.png" title="ScoreSaber" alt="ScoreSaber icon" width="96" />
</p>

<h1 align="center">PC Mod</h1>

The [BSIPA](https://github.com/nike4613/BeatSaber-IPA-Reloaded) plugin for ScoreSaber on PC 

## About this fork

This is a personal, unofficial fork of [ScoreSaber/pc-mod](https://github.com/ScoreSaber/pc-mod), porting the plugin (and its [Legato](https://github.com/ScoreSaber/legato) compatibility dependency) to Beat Saber 1.45.1, which isn't supported by the upstream project yet. It's distributed here under the same [MIT License](LICENSE) as upstream — all credit for the original mod goes to the ScoreSaber team.

**On leaderboard fair play:** before doing this, we checked whether running a self-built copy against a newer game version could be considered cheating or against the rules:

- ScoreSaber's [community rules](https://wiki.scoresaber.com/rules.html) prohibit third-party utilities used *to gain an advantage* (scripts, cheats, bots) — nothing there concerns running a legitimately-built copy of ScoreSaber's own official client.
- More concretely, the client code itself won't let an unofficial build cheat by default: `ScoreSaberApiClient.UploadScore` hard-refuses to submit a score (`"ScoreSaber upload trust is unavailable"`) unless the build carries either real ScoreSaber-issued CI credentials or a development token (see `Core/Api/UploadTrust/`). There's no fallback path around this — it's a real gate, not just a policy.
- ScoreSaber's own README already anticipates exactly this situation: third-party/dev builds are expected to request a dev token from `developers@scoresaber.com` (see below) rather than upload untrusted. Not doing so is called out as "being rude," not cheating.

**Current status: viewing only, no score uploads.** No dev token has been requested for this fork, so per the above, score upload is expected to be refused by the client itself. This build is used for browsing leaderboards and personal stats only — not for submitting scores — until a dev token is requested and granted, if that's ever pursued.

## Local Build Settings

If you want to be able to upload scores from a dev build of ScoreSaber (without being rude about it) you're going to need a dev token. Feel free to contact one of our admins for one. You can find their social contact information [here](https://scoresaber.com/team) of if emails more your thing, here ya go: developers@scoresaber.com

For local MSBuild secrets/settings, copy `Directory.Build.local.props.example` to `Directory.Build.local.props`

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for code standards and pull request expectations


## A note on how this fork was made

I'm not a professional programmer. I do some Android development, but Unity/Harmony
modding is new to me, so I know just enough to spot when something has gone wrong and
roughly how to fix it.

This fork's changes were made with AI assistance. I direct the work, review what it
produces, and test everything on real hardware before it goes into a release. I'm
sharing this because I'd rather be upfront about it than have you wonder. This
disclaimer covers this fork's own changes only — the original mod is the work of its
original author(s).

I understand not everyone is comfortable with AI-assisted code, and that's a fair
position; a lot of people here have spent years building real expertise. If you'd
rather check things yourself, everything is open and the commits are small. Bug
reports, reviews and corrections are very welcome, and I'll fix what I get wrong.
