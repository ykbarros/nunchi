# Nunchi

**눈치** (noon-chee): the art of reading the room. A phone-friendly party game with three ways to play:

| Mode | Plays like | In a sentence |
|---|---|---|
| **Rank** | Top Ten | Everyone secretly gets 1–10, answers a theme to match, and the Captain ranks them. Co-op, with hearts. |
| **Line Up** | Fun Facts | Answer a question about yourself in secret, then line up lowest to highest. Co-op. |
| **Dial** | Wavelength | The Psychic gives one clue for a hidden spot on a spectrum, and the team turns the dial. Teams or co-op. |

Every mode shows its quick rules before you start, and the **?** button brings them back during play.

## Two ways to play
- **One phone:** pass it around. Secrets hide behind press-and-hold peeks.
- **Rooms:** the host taps *Start a room* and shares the 4-letter code or invite link. Everyone joins on their own phone
  and sees only their own secrets. Rooms are peer-to-peer (WebRTC via [PeerJS](https://peerjs.com/)), so there's no server to run.
  The host's phone runs the game, so the host keeps Nunchi open. Anyone who drops can rejoin, and reloading a tab reconnects automatically.

A single self-contained `index.html` with no build step. One-phone mode works offline once loaded.

## Dev notes
- `?net=local` swaps PeerJS for a same-browser BroadcastChannel transport, so you can play a room across several tabs with no internet.
- `?peerhost=127.0.0.1:9000` points PeerJS at a self-hosted PeerServer (`npx peer --port 9000`).
- Decks live at the top of the second `<script>` in `index.html`, one prompt per line.
