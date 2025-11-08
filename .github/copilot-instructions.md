# GitHub Copilot Instructions for Teacher-Tip

## Project Overview

This repository contains **Quiz-Tac-Toe**, an interactive educational game that combines Tic-Tac-Toe gameplay with quiz questions. It's designed for ASU TESOL (Teaching English to Speakers of Other Languages) to create engaging review activities for students.

## Project Structure

- **Single-file application**: `index.html` contains all HTML, CSS, and JavaScript
- **No build process**: This is a static HTML file that runs directly in the browser
- **No dependencies**: Uses CDN-hosted libraries (Tailwind CSS, Google Fonts)

## Technology Stack

- **HTML5**: Semantic markup and structure
- **CSS3**: Custom properties (CSS variables) for theming, animations, and responsive design
- **Tailwind CSS**: Utility-first CSS framework (loaded via CDN)
- **Vanilla JavaScript**: No frameworks - pure ES6+ JavaScript for game logic
- **Google Fonts**: Inter and Orbitron font families

## Code Style and Conventions

### HTML
- Use semantic HTML5 elements
- Maintain clear section comments (e.g., `<!-- SECTION 1: SETUP CONTAINER -->`)
- Keep IDs descriptive and kebab-case (e.g., `game-setup-form`, `player-x-score-box`)
- Use data attributes for dynamic behavior (e.g., `data-cell-index`, `data-index`)

### CSS
- Use CSS custom properties (variables) defined in `:root` for colors and styling
- Follow the existing color scheme:
  - `--x-color`: #007bff (blue) for Team X
  - `--o-color`: #dc3545 (red) for Team O
  - `--bg-color`: #f0f4f8 (light blue-gray background)
- Use Tailwind utility classes for layout and spacing
- Keep custom CSS for animations and game-specific styling
- Responsive design: mobile-first with `md:` breakpoints

### JavaScript
- Use modern ES6+ syntax (const/let, arrow functions, template literals)
- Keep functions focused and well-documented with JSDoc comments
- Follow existing naming conventions:
  - camelCase for variables and functions
  - PascalCase for constructors (if any)
  - UPPERCASE for constants
- Organize code in logical sections with clear comments
- Event delegation pattern for dynamic content

### Game Logic Structure
- **Setup Phase**: Form-based configuration where teachers create questions
- **Game Phase**: Tic-Tac-Toe board with quiz questions in each cell
- **Question Types**:
  - Multiple choice (4 options)
  - Open-ended (text input with exact match validation)
- **Scoring**: Track wins for Team X and Team O across multiple rounds

## Key Features to Preserve

1. **Editable Setup**: Teachers can customize the game title and all 9 cells with multiple questions each
2. **Dynamic Question Management**: Add/remove questions during setup
3. **Modal-based Quizzing**: Questions appear in a modal when cells are clicked
4. **Answer Validation**: Both MC and open-ended answer checking with feedback
5. **Score Tracking**: Persistent scoring across rounds
6. **Responsive Design**: Works on mobile and desktop devices
7. **Visual Feedback**: Animations for placing X/O markers and answer feedback

## Important Implementation Details

### Data Structure
```javascript
gameData = {
    title: "QUIZ-TAC-TOE",
    cells: [
        {
            questions: [
                { type: 'mc', question: '...', options: [...], correct: 0 },
                { type: 'open', question: '...', answer: '...' }
            ]
        }
        // ... 9 cells total
    ]
}
```

### Game State
- `currentPlayer`: 'X' or 'O'
- `board`: Array of 9 elements (null, 'X', or 'O')
- `scores`: Object with X and O win counts
- `currentQuestionIndex`: Track multi-question progress per cell

## Development Guidelines

### When Making Changes:
1. **Test thoroughly**: This is a single-file app, so changes affect everything
2. **Preserve animations**: The game uses CSS animations for better UX
3. **Maintain accessibility**: Keep keyboard navigation and screen reader support in mind
4. **Mobile-first**: Ensure responsive design works on all screen sizes
5. **No external dependencies**: Keep everything self-contained in one HTML file

### Common Tasks:
- **Adding new question types**: Extend both setup form and modal validation logic
- **Styling changes**: Use existing CSS variables when possible
- **Adding features**: Keep the single-file structure; use sections/comments for organization
- **Bug fixes**: Check both setup phase and game phase behavior

### Testing Approach:
- **Manual testing only**: No automated testing framework
- **Test in browser**: Open `index.html` directly in a web browser
- **Cross-browser testing**: Test in Chrome, Firefox, Safari, and Edge
- **Mobile testing**: Use browser dev tools responsive mode and actual mobile devices

## Educational Context

This tool is designed for **language teachers** (TESOL) to create review games. Consider:
- Keep the interface intuitive for non-technical users
- Make setup process clear and forgiving
- Provide helpful feedback for incorrect answers
- Maintain the fun, game-like atmosphere

## Deployment

This is a **static website** that can be deployed by:
- Opening `index.html` in a browser
- Hosting on GitHub Pages
- Any static web hosting service

No build step or server required!
