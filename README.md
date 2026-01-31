# Flight Search Engine

A modern, responsive Flight Search Engine web application built with Angular 19.

## Features

- ✈️ **Flight Search**: Search flights by origin, destination, and dates
- 🔍 **Advanced Filtering**: Filter by stops, price range, airlines, and departure time
- 📊 **Live Price Graph**: Real-time price trends visualization
- 📱 **Responsive Design**: Works seamlessly on desktop and mobile
- 🎨 **Modern UI**: Clean, intuitive interface with smooth animations
- ⚡ **Performance**: Optimized with debounced filters and efficient state management

## Tech Stack

- **Angular 19** - Latest Angular framework
- **TypeScript** - Strict typing enabled
- **SCSS** - Styling with modern CSS features
- **RxJS** - Reactive state management
- **Chart.js / ng2-charts** - Data visualization
- **Amadeus Self-Service API** - Flight data (with mock fallback)

## Project Structure

```
src/app
 ├── modules
 │    ├── search          # Search form with autocomplete
 │    ├── results         # Flight results with sorting & pagination
 │    ├── filters         # Filter panel with multiple filter types
 │    └── charts          # Live price graph component
 ├── services
 │    ├── flight-api.service.ts      # API integration
 │    ├── search-state.service.ts    # Search state management
 │    └── filter.service.ts          # Filter logic
 ├── models
 │    ├── flight.model.ts
 │    ├── segment.model.ts
 │    ├── price.model.ts
 │    ├── airport.model.ts
 │    ├── search-params.model.ts
 │    └── filter.model.ts
 ├── shared
 │    └── components
 │         ├── loading-skeleton
 │         └── empty-state
 └── pages
      └── results-page    # Results page layout
```

## Getting Started

### Prerequisites

- Node.js 18+ and npm
- Angular CLI 19+

### Installation

1. Install dependencies:
```bash
npm install
```

2. Configure API (optional):
   - Update `flight-api.service.ts` with your Amadeus API credentials
   - Or use the built-in mock data for development

3. Start development server:
```bash
npm start
```

4. Open browser:
   Navigate to `http://localhost:4200`

## Usage

1. **Search Flights**:
   - Enter origin and destination (autocomplete available)
   - Select departure and return dates
   - Choose passengers and cabin class
   - Click "Search Flights"

2. **Filter Results**:
   - Use the filter panel to refine results
   - Filters work simultaneously (AND logic)
   - Price graph updates in real-time

3. **Sort Results**:
   - Sort by price, duration, or departure time
   - Results update instantly

4. **View Price Graph**:
   - See price trends for filtered flights
   - Graph updates automatically with filter changes

## Features in Detail

### Search Module
- Airport/city autocomplete with debouncing
- Form validation
- Trip type selection (one-way/round-trip)
- Date validation

### Results Module
- Flight cards with detailed information
- Sorting options
- Pagination
- Highlights for cheapest and fastest flights
- Loading skeletons
- Empty states

### Filters Module
- Stops filter (non-stop, 1 stop, 2+ stops)
- Price range slider
- Airline multi-select
- Time range filter (morning/afternoon/evening)
- Reset filters option

### Charts Module
- Live price graph
- Min/Max/Average price indicators
- Updates in real-time with filters
- Collapsible on mobile

## Responsive Design

- **Desktop**: Sidebar filters, full-width results, top chart
- **Mobile**: Modal filters, stacked results, collapsible chart
- Touch-friendly interactions
- No horizontal scrolling

## Development

### Build

```bash
npm run build
```

### Test

```bash
npm test
```

## API Configuration

To use real Amadeus API data:

1. Get API credentials from [Amadeus Self-Service](https://developers.amadeus.com/)
2. Update `flight-api.service.ts`:
   ```typescript
   private readonly apiKey = 'YOUR_API_KEY';
   private readonly apiSecret = 'YOUR_API_SECRET';
   ```

The app includes mock data fallback for development.

## Architecture Highlights

- **Modular Design**: Independent, reusable modules
- **Reactive State**: RxJS BehaviorSubjects for state management
- **Type Safety**: Strict TypeScript with no `any` types
- **Performance**: Debounced filters, memoized calculations
- **UX Polish**: Loading states, error handling, smooth transitions

## License

MIT
