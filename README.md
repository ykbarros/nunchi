# Nunchi

Read the room to win the game. A phone-friendly party game with three games in one:

- **Top Ten:** act out the theme to match your secret number from 1 to 10, then see if the Captain ranks you right.
- **Fun Facts:** answer questions about yourselves in secret, then line up by how well you know each other.
- **Wavelength:** give a clue that hits the hidden spot on the dial, then see if your team is on your wavelength.

Every game can be played all together or as two teams. Short rules show before you start, and the **?** button brings them back mid-game.

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
