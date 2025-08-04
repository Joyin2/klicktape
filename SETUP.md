# Klicktape Web Setup

## Environment Configuration

### 1. Supabase Configuration
Copy the template and add your credentials:

```bash
cp public/config.template.js public/config.js
```

Then edit `public/config.js` with your actual Supabase credentials:

```javascript
const SUPABASE_CONFIG = {
    url: 'https://your-project.supabase.co',
    anonKey: 'your-anon-key-here'
};
```

### 2. Environment Variables (.env)
```
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_ANON_KEY=your-anon-key-here
NODE_ENV=development
PORT=8000
```

## Running the Application

### Development
```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx http-server public -p 8000

# Using Firebase
firebase serve
```

### Production
```bash
firebase deploy
```

## Security Notes

- ✅ `config.js` is in `.gitignore` - never commit real credentials
- ✅ Use `config.template.js` as reference for team members
- ✅ For production, consider using build-time environment variable replacement
- ✅ Supabase anon keys are safe for frontend use (with proper RLS policies)

## Supabase Setup

1. **Authentication → URL Configuration**
   - Add your domain to redirect URLs
   - For local development: `http://192.168.31.241:8000/reset-password.html`
   - For production: `https://your-domain.com/reset-password.html`

2. **Row Level Security (RLS)**
   - Enable RLS on all tables
   - Create policies for user data access
